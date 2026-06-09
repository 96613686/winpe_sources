# Windows::Internal::Async::SuspendDispatchQueue::RuntimeClassInitialize(void)

- ea: `0x1800733f8`
- end: `0x1800734c8`
- name: `?RuntimeClassInitialize@SuspendDispatchQueue@Async@Internal@Windows@@QEAAJXZ`
- size: `208`
- prototype: `__int64 __fastcall(Windows::Internal::Async::SuspendDispatchQueue *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007008c`

## callees

- `0x18000ce48`
- `0x1800733f8`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18007342f`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x18007342f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007345b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007345b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007348d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007348d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007349c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007349c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Async::SuspendDispatchQueue::RuntimeClassInitialize(LPVOID *this)
{
  __int64 result; // rax
  HRESULT v3; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  IID rclsid; // [rsp+30h] [rbp-28h] BYREF

  *(_QWORD *)&rclsid.Data1 = 854;
  *(_DWORD *)rclsid.Data4 = 192;
  *(_DWORD *)&rclsid.Data4[4] = 1174405120;
  result = CoIncrementMTAUsage(this + 10);
  if ( (int)result >= 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this + 14);
    v3 = CoCreateInstance(&rclsid, 0, 1u, &GUID_953c92df_3741_4bb4_9979_c618d6fe0af2, this + 14);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *, char *))(*(_QWORD *)this[14] + 24LL))(
             this[14],
             this,
             (char *)this + 104);
      if ( v3 >= 0 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        this[3] = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800733f8  push    rbp
0x1800733fa  push    rbx
0x1800733fb  push    rsi
0x1800733fc  push    rdi
0x1800733fd  mov     rbp, rsp
0x180073400  sub     rsp, 58h
0x180073404  mov     rax, cs:__security_cookie
0x18007340b  xor     rax, rsp
0x18007340e  mov     [rbp+var_18], rax
0x180073412  mov     rdi, rcx
0x180073415  mov     qword ptr [rbp+rclsid.Data1], 356h
0x18007341d  add     rcx, 50h ; 'P'
0x180073421  mov     dword ptr [rbp+rclsid.Data4], 0C0h
0x180073428  mov     dword ptr [rbp+rclsid.Data4+4], 46000000h
0x18007342f  call    cs:__imp_CoIncrementMTAUsage
0x180073435  test    eax, eax
0x180073437  js      short loc_1800734B3
0x180073439  lea     rsi, [rdi+70h]
0x18007343d  mov     rcx, rsi
0x180073440  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180073445  xor     edx, edx; pUnkOuter
0x180073447  mov     [rsp+58h+ppv], rsi; ppv
0x18007344c  lea     r9, _GUID_953c92df_3741_4bb4_9979_c618d6fe0af2; riid
0x180073453  lea     rcx, [rbp+rclsid]; rclsid
0x180073457  lea     r8d, [rdx+1]; dwClsContext
0x18007345b  call    cs:__imp_CoCreateInstance
0x180073461  mov     ebx, eax
0x180073463  test    eax, eax
0x180073465  js      short loc_1800734B1
0x180073467  mov     rcx, [rsi]
0x18007346a  lea     r8, [rdi+68h]
0x18007346e  mov     rdx, rdi
0x180073471  mov     rax, [rcx]
0x180073474  mov     rax, [rax+18h]
0x180073478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007347d  mov     ebx, eax
0x18007347f  test    eax, eax
0x180073481  js      short loc_1800734B1
0x180073483  xor     r9d, r9d; lpName
0x180073486  xor     r8d, r8d; bInitialState
0x180073489  xor     edx, edx; bManualReset
0x18007348b  xor     ecx, ecx; lpEventAttributes
0x18007348d  call    cs:__imp_CreateEventW
0x180073493  mov     [rdi+18h], rax
0x180073497  test    rax, rax
0x18007349a  jnz     short loc_1800734B1
0x18007349c  call    cs:__imp_GetLastError
0x1800734a2  mov     ebx, eax
0x1800734a4  test    eax, eax
0x1800734a6  jle     short loc_1800734B1
0x1800734a8  movzx   ebx, ax
0x1800734ab  or      ebx, 80070000h
0x1800734b1  mov     eax, ebx
0x1800734b3  mov     rcx, [rbp+var_18]
0x1800734b7  xor     rcx, rsp; StackCookie
0x1800734ba  call    __security_check_cookie
0x1800734bf  add     rsp, 58h
0x1800734c3  pop     rdi
0x1800734c4  pop     rsi
0x1800734c5  pop     rbx
0x1800734c6  pop     rbp
0x1800734c7  retn
```
