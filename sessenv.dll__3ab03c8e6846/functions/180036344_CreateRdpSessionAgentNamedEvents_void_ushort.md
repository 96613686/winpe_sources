# CreateRdpSessionAgentNamedEvents(void * *,ushort * *)

- ea: `0x180036344`
- end: `0x180036559`
- name: `?CreateRdpSessionAgentNamedEvents@@YAJPEAPEAXPEAPEAG@Z`
- size: `533`
- prototype: `__int64 __fastcall(void **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037e30`

## callees

- `0x180003f30`
- `0x180017b30`
- `0x18001a280`
- `0x18001ad5c`
- `0x180036344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003641f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003641f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036496`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036514`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036514`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036486`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180036486`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800363b5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800363b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036502`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800363ea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800363ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003652d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003652d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036415`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180036415`

## string_xrefs

- `0x1800363cb`: `CreateRdpSessionAgentNamedEvents`
- `0x1800363c1`: `CoCreateGuid failed: 0x%x in %s`
- `0x1800363f6`: `StringFromCLSID failed: 0x%x in %s`
- `0x1800364b7`: `CreateEventW failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CreateRdpSessionAgentNamedEvents(void **a1, unsigned __int16 **a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  const char *v6; // rdx
  signed int LastError; // eax
  unsigned __int64 v8; // rdi
  HANDLE v9; // rax
  signed int v10; // eax
  unsigned __int64 i; // rcx
  unsigned __int64 j; // rdi
  HANDLE v13; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-99h] BYREF
  __int64 SecurityDescriptorSize; // [rsp+28h] [rbp-91h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-89h] BYREF
  HANDLE hObject[2]; // [rsp+38h] [rbp-81h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+48h] [rbp-71h] BYREF
  GUID pguid; // [rsp+60h] [rbp-59h] BYREF
  WCHAR Name[64]; // [rsp+70h] [rbp-49h] BYREF

  lpsz = 0;
  pguid = 0;
  memset_0(Name, 0, sizeof(Name));
  SecurityDescriptor = 0;
  *(_OWORD *)hObject = 0;
  LODWORD(SecurityDescriptorSize) = 0;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v4 = CoCreateGuid(&pguid);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "CoCreateGuid failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v6, (unsigned int)v4, "CreateRdpSessionAgentNamedEvents", lpsz, SecurityDescriptorSize);
    goto LABEL_23;
  }
  v4 = StringFromCLSID(&pguid, &lpsz);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = "StringFromCLSID failed: 0x%x in %s";
    goto LABEL_3;
  }
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:SYG:SYD:(A;;0x1F0003;;;SY)",
          1u,
          &SecurityDescriptor,
          (PULONG)&SecurityDescriptorSize) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  v8 = 0;
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
  EventAttributes.nLength = 24;
  EventAttributes.bInheritHandle = 0;
  while ( v8 < 2 )
  {
    v4 = StringCchPrintfW(Name, 0x40u, off_18005F190[v8], lpsz);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = "StringCchPrintf failed: 0x%x in %s";
      goto LABEL_3;
    }
    v9 = CreateEventW(&EventAttributes, 1, 0, Name);
    hObject[v8] = v9;
    if ( !v9 )
    {
      v10 = GetLastError();
      v5 = v10;
      if ( v10 > 0 )
        v5 = (unsigned __int16)v10 | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "CreateEventW failed: 0x%x in %s", v5, "CreateRdpSessionAgentNamedEvents");
        goto LABEL_23;
      }
    }
    ++v8;
  }
  for ( i = 0; i < 2; ++i )
  {
    a1[i] = hObject[i];
    hObject[i] = 0;
  }
  *a2 = lpsz;
  lpsz = 0;
LABEL_23:
  CoTaskMemFree(lpsz);
  for ( j = 0; j < 2; ++j )
  {
    v13 = hObject[j];
    if ( v13 )
      CloseHandle(v13);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x180036344  mov     [rsp-8+arg_10], rbx
0x180036349  mov     [rsp-8+arg_18], rsi
0x18003634e  push    rbp
0x18003634f  push    rdi
0x180036350  push    r14
0x180036352  lea     rbp, [rsp-47h]
0x180036357  sub     rsp, 100h
0x18003635e  mov     rax, cs:__security_cookie
0x180036365  xor     rax, rsp
0x180036368  mov     [rbp+57h+var_20], rax
0x18003636c  mov     rsi, rdx
0x18003636f  mov     [rsp+110h+lpsz], 0
0x180036378  mov     r14, rcx
0x18003637b  xorps   xmm0, xmm0
0x18003637e  xor     edx, edx; Val
0x180036380  lea     rcx, [rbp+57h+Name]; void *
0x180036384  mov     r8d, 80h; Size
0x18003638a  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18003638e  call    memset_0
0x180036393  xor     eax, eax
0x180036395  lea     rcx, [rbp+57h+pguid]; pguid
0x180036399  xorps   xmm0, xmm0
0x18003639c  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], rax
0x1800363a0  xorps   xmm1, xmm1
0x1800363a3  mov     [rsp+110h+SecurityDescriptor], rax
0x1800363a8  movups  xmmword ptr [rsp+110h+hObject], xmm0
0x1800363ad  mov     dword ptr [rsp+110h+SecurityDescriptorSize], eax
0x1800363b1  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm1
0x1800363b5  call    cs:__imp_CoCreateGuid
0x1800363bb  mov     ebx, eax
0x1800363bd  test    eax, eax
0x1800363bf  jns     short loc_1800363E1
0x1800363c1  lea     rdx, aCocreateguidFa; "CoCreateGuid failed: 0x%x in %s"
0x1800363c8  mov     r8d, eax
0x1800363cb  lea     r9, aCreaterdpsessi; "CreateRdpSessionAgentNamedEvents"
0x1800363d2  mov     ecx, 8; int
0x1800363d7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800363dc  jmp     loc_1800364FD
0x1800363e1  lea     rdx, [rsp+110h+lpsz]; lplpsz
0x1800363e6  lea     rcx, [rbp+57h+pguid]; rclsid
0x1800363ea  call    cs:__imp_StringFromCLSID
0x1800363f0  mov     ebx, eax
0x1800363f2  test    eax, eax
0x1800363f4  jns     short loc_1800363FF
0x1800363f6  lea     rdx, aStringfromclsi; "StringFromCLSID failed: 0x%x in %s"
0x1800363fd  jmp     short loc_1800363C8
0x1800363ff  lea     r9, [rsp+110h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180036404  mov     edx, 1; StringSDRevision
0x180036409  lea     r8, [rsp+110h+SecurityDescriptor]; SecurityDescriptor
0x18003640e  lea     rcx, aOSygSydA0x1f00; "O:SYG:SYD:(A;;0x1F0003;;;SY)"
0x180036415  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003641b  test    eax, eax
0x18003641d  jnz     short loc_180036434
0x18003641f  call    cs:__imp_GetLastError
0x180036425  mov     ebx, eax
0x180036427  test    eax, eax
0x180036429  jle     short loc_180036434
0x18003642b  movzx   ebx, ax
0x18003642e  or      ebx, 80070000h
0x180036434  mov     rax, [rsp+110h+SecurityDescriptor]
0x180036439  xor     edi, edi
0x18003643b  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x18003643f  mov     [rbp+57h+EventAttributes.nLength], 18h
0x180036446  mov     [rbp+57h+EventAttributes.bInheritHandle], 0
0x18003644d  cmp     rdi, 2
0x180036451  jnb     short loc_1800364CF
0x180036453  mov     r9, [rsp+110h+lpsz]
0x180036458  lea     r8, off_18005F190; "Global\\RdpSaEventReady-%s"
0x18003645f  mov     r8, [r8+rdi*8]; unsigned __int16 *
0x180036463  lea     rcx, [rbp+57h+Name]; unsigned __int16 *
0x180036467  mov     edx, 40h ; '@'; unsigned __int64
0x18003646c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036471  mov     ebx, eax
0x180036473  test    eax, eax
0x180036475  js      short loc_1800364C3
0x180036477  xor     r8d, r8d; bInitialState
0x18003647a  lea     r9, [rbp+57h+Name]; lpName
0x18003647e  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x180036482  lea     edx, [r8+1]; bManualReset
0x180036486  call    cs:__imp_CreateEventW
0x18003648c  mov     [rsp+rdi*8+110h+hObject], rax
0x180036491  test    rax, rax
0x180036494  jnz     short loc_1800364AF
0x180036496  call    cs:__imp_GetLastError
0x18003649c  mov     ebx, eax
0x18003649e  test    eax, eax
0x1800364a0  jle     short loc_1800364AB
0x1800364a2  movzx   ebx, ax
0x1800364a5  or      ebx, 80070000h
0x1800364ab  test    ebx, ebx
0x1800364ad  js      short loc_1800364B4
0x1800364af  inc     rdi
0x1800364b2  jmp     short loc_18003644D
0x1800364b4  mov     r8d, ebx
0x1800364b7  lea     rdx, aCreateeventwFa; "CreateEventW failed: 0x%x in %s"
0x1800364be  jmp     loc_1800363CB
0x1800364c3  lea     rdx, aStringcchprint; "StringCchPrintf failed: 0x%x in %s"
0x1800364ca  jmp     loc_1800363C8
0x1800364cf  xor     ecx, ecx
0x1800364d1  mov     rax, [rsp+rcx*8+110h+hObject]
0x1800364d6  mov     [r14+rcx*8], rax
0x1800364da  mov     [rsp+rcx*8+110h+hObject], 0
0x1800364e3  inc     rcx
0x1800364e6  cmp     rcx, 2
0x1800364ea  jb      short loc_1800364D1
0x1800364ec  mov     rax, [rsp+110h+lpsz]
0x1800364f1  mov     [rsi], rax
0x1800364f4  mov     [rsp+110h+lpsz], 0
0x1800364fd  mov     rcx, [rsp+110h+lpsz]; pv
0x180036502  call    cs:__imp_CoTaskMemFree
0x180036508  xor     edi, edi
0x18003650a  mov     rcx, [rsp+rdi*8+110h+hObject]; hObject
0x18003650f  test    rcx, rcx
0x180036512  jz      short loc_18003651A
0x180036514  call    cs:__imp_CloseHandle
0x18003651a  inc     rdi
0x18003651d  cmp     rdi, 2
0x180036521  jb      short loc_18003650A
0x180036523  mov     rcx, [rsp+110h+SecurityDescriptor]; hMem
0x180036528  test    rcx, rcx
0x18003652b  jz      short loc_180036533
0x18003652d  call    cs:__imp_LocalFree
0x180036533  mov     eax, ebx
0x180036535  mov     rcx, [rbp+57h+var_20]
0x180036539  xor     rcx, rsp; StackCookie
0x18003653c  call    __security_check_cookie
0x180036541  lea     r11, [rsp+110h+var_10]
0x180036549  mov     rbx, [r11+30h]
0x18003654d  mov     rsi, [r11+38h]
0x180036551  mov     rsp, r11
0x180036554  pop     r14
0x180036556  pop     rdi
0x180036557  pop     rbp
0x180036558  retn
```
