# HANDLE_OBJECT::CreateInvalidNotificationEvent(void)

- ea: `0x180013d70`
- end: `0x180013e3c`
- name: `?CreateInvalidNotificationEvent@HANDLE_OBJECT@@QEAAKXZ`
- size: `204`
- prototype: `unsigned int __fastcall(HANDLE_OBJECT *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180011b98`
- `0x1800600c0`

## callees

- `0x180013d70`
- `0x1800a1d10`
- `0x1800cf58c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013da3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013df7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013e34`
- `ntdll!RtlNtStatusToDosError` at `0x180013e03`
- `ntdll!RtlNtStatusToDosError` at `0x180013e03`
- `ntdll!NtSetInformationObject` at `0x180013dc8`
- `ntdll!NtSetInformationObject` at `0x180013dc8`

## pseudocode

```c
__int64 __fastcall HANDLE_OBJECT::CreateInvalidNotificationEvent(HANDLE_OBJECT *this)
{
  HANDLE EventW; // rax
  void *v3; // rdi
  int v4; // eax
  ULONG v5; // ebx
  __int16 ObjectInformation; // [rsp+30h] [rbp-18h] BYREF

  ObjectInformation = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v3 = EventW;
  if ( EventW )
  {
    HIBYTE(ObjectInformation) = 1;
    v4 = NtSetInformationObject(EventW, ObjectHandleFlagInformation, &ObjectInformation, 2u);
    if ( v4 < 0 )
    {
      v5 = RtlNtStatusToDosError(v4);
      if ( (BYTE2(xmmword_180107A60) & 2) != 0 )
        WPP_SF_qD(1041, 26, WPP_989094c1a00a31c88345b82a0793d746_Traceguids, v3);
      CloseHandle(v3);
    }
    else
    {
      v5 = 0;
      *((_QWORD *)this + 11) = v3;
    }
  }
  else
  {
    return GetLastError();
  }
  return v5;
}

```

## disassembly

```asm
0x180013d70  mov     [rsp+arg_8], rbx
0x180013d75  mov     [rsp+arg_10], rsi
0x180013d7a  push    rdi
0x180013d7b  sub     rsp, 40h
0x180013d7f  mov     rax, cs:__security_cookie
0x180013d86  xor     rax, rsp
0x180013d89  mov     [rsp+48h+var_10], rax
0x180013d8e  xor     eax, eax
0x180013d90  mov     rsi, rcx
0x180013d93  xor     r9d, r9d; lpName
0x180013d96  mov     [rsp+48h+ObjectInformation], ax
0x180013d9b  xor     r8d, r8d; bInitialState
0x180013d9e  xor     ecx, ecx; lpEventAttributes
0x180013da0  lea     edx, [rax+1]; bManualReset
0x180013da3  call    cs:__imp_CreateEventW
0x180013da9  mov     rdi, rax
0x180013dac  test    rax, rax
0x180013daf  jz      short loc_180013DF7
0x180013db1  mov     r9d, 2; Length
0x180013db7  mov     byte ptr [rsp+48h+ObjectInformation+1], 1
0x180013dbc  lea     r8, [rsp+48h+ObjectInformation]; ObjectInformation
0x180013dc1  mov     rcx, rax; ObjectHandle
0x180013dc4  lea     edx, [r9+2]; ObjectInformationClass
0x180013dc8  call    cs:__imp_NtSetInformationObject
0x180013dce  test    eax, eax
0x180013dd0  js      short loc_180013E01
0x180013dd2  xor     ebx, ebx
0x180013dd4  mov     [rsi+58h], rdi
0x180013dd8  mov     eax, ebx
0x180013dda  mov     rcx, [rsp+48h+var_10]
0x180013ddf  xor     rcx, rsp; StackCookie
0x180013de2  call    __security_check_cookie
0x180013de7  mov     rbx, [rsp+48h+arg_8]
0x180013dec  mov     rsi, [rsp+48h+arg_10]
0x180013df1  add     rsp, 40h
0x180013df5  pop     rdi
0x180013df6  retn
0x180013df7  call    cs:__imp_GetLastError
0x180013dfd  mov     ebx, eax
0x180013dff  jmp     short loc_180013DD8
0x180013e01  mov     ecx, eax; Status
0x180013e03  call    cs:__imp_RtlNtStatusToDosError
0x180013e09  mov     ebx, eax
0x180013e0b  test    byte ptr cs:xmmword_180107A60+2, 2
0x180013e12  jz      short loc_180013E31
0x180013e14  mov     edx, 1Ah
0x180013e19  mov     [rsp+48h+var_28], eax
0x180013e1d  mov     ecx, 411h
0x180013e22  lea     r8, WPP_989094c1a00a31c88345b82a0793d746_Traceguids
0x180013e29  mov     r9, rdi
0x180013e2c  call    WPP_SF_qD
0x180013e31  mov     rcx, rdi; hObject
0x180013e34  call    cs:__imp_CloseHandle
0x180013e3a  jmp     short loc_180013DD8
```
