# RtmApiStartup

- ea: `0x180007a34`
- end: `0x180007c3c`
- name: `RtmApiStartup`
- size: `520`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004300`
- `0x180004920`
- `0x180004b50`
- `0x1800052d0`
- `0x180005530`
- `0x180008230`
- `0x1800084c0`
- `0x180008710`
- `0x18000aef0`

## callees

- `0x180002c5c`
- `0x180004920`
- `0x1800052d0`
- `0x180007a34`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180007a7c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180007a7c`
- `ntdll!RtlReleaseResource` at `0x180007c19`
- `ntdll!RtlReleaseResource` at `0x180007c19`
- `KERNEL32!HeapAlloc` at `0x180007ab8`
- `KERNEL32!HeapAlloc` at `0x180007ab8`
- `KERNEL32!GetProcessHeap` at `0x180007aa2`
- `KERNEL32!GetProcessHeap` at `0x180007be7`
- `KERNEL32!GetProcessHeap` at `0x180007aa2`
- `KERNEL32!GetProcessHeap` at `0x180007be7`
- `KERNEL32!HeapFree` at `0x180007bf9`
- `KERNEL32!HeapFree` at `0x180007bf9`
- `rtutils!RouterLogDeregisterA` at `0x180007c06`
- `rtutils!RouterLogDeregisterA` at `0x180007c06`
- `rtutils!RouterLogRegisterA` at `0x180007a95`
- `rtutils!RouterLogRegisterA` at `0x180007a95`

## string_xrefs

- `0x180007ad7`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\RoutingTableManager`
- `0x180007b33`: `RtmApiStartup: Failed to copy memory with error: %x`

## pseudocode

```c
__int64 RtmApiStartup()
{
  unsigned int InstanceConfig; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v2; // rdi
  LPCSTR v3; // r9
  __int64 v4; // rax
  CHAR *v5; // rcx
  const char *v6; // rdx
  CHAR *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  HANDLE v10; // rax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-C8h] BYREF
  int *v13; // [rsp+48h] [rbp-B8h]
  int v14; // [rsp+50h] [rbp-B0h]
  int v15; // [rsp+54h] [rbp-ACh]
  int v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  InstanceConfig = 0;
  RtlAcquireResourceExclusive(&Resource, 1u);
  if ( !(_DWORD)qword_18002BD00 )
  {
    hLogHandle = RouterLogRegisterA("RTM");
    ProcessHeap = GetProcessHeap();
    v2 = 260;
    InstanceConfig = 8;
    lpSubKey = (LPCSTR)HeapAlloc(ProcessHeap, 8u, 0x104u);
    v3 = lpSubKey;
    if ( lpSubKey )
    {
      v4 = 67;
      v5 = (CHAR *)lpSubKey;
      v6 = "SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\RoutingTableManager";
      do
      {
        if ( !v4 )
          break;
        if ( !*v6 )
          break;
        *v5++ = *v6++;
        --v4;
        --v2;
      }
      while ( v2 );
      v7 = v5 - 1;
      if ( v2 )
        v7 = v5;
      *v7 = 0;
      if ( v2 )
      {
        qword_18002BD00 = 1;
        qword_18002BD10 = (__int64)qword_18002BD08;
        qword_18002BD08[0] = (__int64)qword_18002BD08;
        InstanceConfig = RtmReadInstanceConfig();
        if ( !InstanceConfig )
          goto LABEL_20;
        InstanceConfig = RtmWriteDefaultConfig();
        if ( !InstanceConfig )
          goto LABEL_20;
      }
      else
      {
        *v3 = 0;
        InstanceConfig = 122;
        if ( (byte_18002BD1A & 4) != 0 )
        {
          LOWORD(v16) = 0;
          FormatRRASErrorString(&v16, L"RtmApiStartup: Failed to copy memory with error: %x", 122);
          if ( (byte_18002BD1A & 4) != 0 )
          {
            v9 = -1;
            do
              ++v9;
            while ( *(_WORD *)&v17[2 * v9 - 4] );
            v15 = 0;
            v14 = 2 * v9 + 2;
            v13 = &v16;
            McGenEventWrite_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RRAS_RTM_TRACE_ERROR,
              v8,
              2u,
              &v12);
          }
        }
      }
    }
    if ( lpSubKey )
    {
      v10 = GetProcessHeap();
      HeapFree(v10, 0, (LPVOID)lpSubKey);
    }
    RouterLogDeregisterA(hLogHandle);
    LODWORD(qword_18002BD00) = 0;
  }
LABEL_20:
  RtlReleaseResource(&Resource);
  return InstanceConfig;
}

```

## disassembly

```asm
0x180007a34  push    rbp
0x180007a36  push    rbx
0x180007a37  push    rsi
0x180007a38  push    rdi
0x180007a39  lea     rbp, [rsp-778h]
0x180007a41  sub     rsp, 878h
0x180007a48  mov     rax, cs:__security_cookie
0x180007a4f  xor     rax, rsp
0x180007a52  mov     [rbp+790h+var_30], rax
0x180007a59  xor     esi, esi
0x180007a5b  lea     rcx, [rsp+890h+var_82C]; void *
0x180007a60  xor     edx, edx; Val
0x180007a62  mov     [rsp+890h+var_830], esi
0x180007a66  mov     r8d, 7FCh; Size
0x180007a6c  call    memset_0
0x180007a71  mov     dl, 1; Wait
0x180007a73  lea     rcx, Resource; Resource
0x180007a7a  mov     ebx, esi
0x180007a7c  call    cs:__imp_RtlAcquireResourceExclusive
0x180007a82  cmp     dword ptr cs:qword_18002BD00, esi
0x180007a88  jnz     loc_180007C12
0x180007a8e  lea     rcx, szSource; "RTM"
0x180007a95  call    cs:__imp_RouterLogRegisterA
0x180007a9b  mov     cs:hLogHandle, rax
0x180007aa2  call    cs:__imp_GetProcessHeap
0x180007aa8  mov     edi, 104h
0x180007aad  lea     ebx, [rsi+8]
0x180007ab0  mov     rcx, rax; hHeap
0x180007ab3  mov     r8d, edi; dwBytes
0x180007ab6  mov     edx, ebx; dwFlags
0x180007ab8  call    cs:__imp_HeapAlloc
0x180007abe  mov     cs:lpSubKey, rax
0x180007ac5  mov     r9, rax
0x180007ac8  test    rax, rax
0x180007acb  jz      loc_180007BDE
0x180007ad1  lea     eax, [rsi+43h]
0x180007ad4  mov     rcx, r9
0x180007ad7  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180007ade  test    rax, rax
0x180007ae1  jz      short loc_180007AFD
0x180007ae3  mov     r8b, [rdx]
0x180007ae6  test    r8b, r8b
0x180007ae9  jz      short loc_180007AFD
0x180007aeb  mov     [rcx], r8b
0x180007aee  inc     rdx
0x180007af1  inc     rcx
0x180007af4  dec     rax
0x180007af7  sub     rdi, 1
0x180007afb  jnz     short loc_180007ADE
0x180007afd  test    rdi, rdi
0x180007b00  lea     rax, [rcx-1]
0x180007b04  cmovnz  rax, rcx
0x180007b08  mov     [rax], sil
0x180007b0b  jnz     loc_180007BA1
0x180007b11  neg     rdi
0x180007b14  mov     [r9], sil
0x180007b17  sbb     ebx, ebx
0x180007b19  not     ebx
0x180007b1b  and     ebx, 7Ah
0x180007b1e  test    cs:byte_18002BD1A, 4
0x180007b25  jz      loc_180007BDE
0x180007b2b  mov     r8d, ebx
0x180007b2e  mov     word ptr [rsp+890h+var_830], si
0x180007b33  lea     rdx, aRtmapistartupF; "RtmApiStartup: Failed to copy memory wi"...
0x180007b3a  lea     rcx, [rsp+890h+var_830]
0x180007b3f  call    FormatRRASErrorString
0x180007b44  test    cs:byte_18002BD1A, 4
0x180007b4b  jz      loc_180007BDE
0x180007b51  lea     rcx, [rsp+890h+var_830]
0x180007b56  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007b5a  inc     rax
0x180007b5d  cmp     [rcx+rax*2], si
0x180007b61  jnz     short loc_180007B5A
0x180007b63  lea     eax, ds:2[rax*2]
0x180007b6a  mov     [rsp+890h+var_83C], esi
0x180007b6e  lea     rcx, [rsp+890h+var_830]
0x180007b73  mov     [rsp+890h+var_840], eax
0x180007b77  lea     rax, [rsp+890h+var_858]
0x180007b7c  mov     [rsp+890h+var_848], rcx
0x180007b81  mov     r9d, 2
0x180007b87  mov     [rsp+890h+var_870], rax
0x180007b8c  lea     rdx, RRAS_RTM_TRACE_ERROR
0x180007b93  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007b9a  call    McGenEventWrite_EventWriteTransfer
0x180007b9f  jmp     short loc_180007BDE
0x180007ba1  lea     rax, qword_18002BD08
0x180007ba8  mov     cs:qword_18002BD00, 1
0x180007bb3  xor     ecx, ecx
0x180007bb5  mov     cs:qword_18002BD10, rax
0x180007bbc  lea     rdx, [rsp+890h+var_860]
0x180007bc1  mov     cs:qword_18002BD08, rax
0x180007bc8  call    RtmReadInstanceConfig
0x180007bcd  mov     ebx, eax
0x180007bcf  test    eax, eax
0x180007bd1  jz      short loc_180007C12
0x180007bd3  call    RtmWriteDefaultConfig
0x180007bd8  mov     ebx, eax
0x180007bda  test    eax, eax
0x180007bdc  jz      short loc_180007C12
0x180007bde  cmp     cs:lpSubKey, rsi
0x180007be5  jz      short loc_180007BFF
0x180007be7  call    cs:__imp_GetProcessHeap
0x180007bed  mov     r8, cs:lpSubKey; lpMem
0x180007bf4  xor     edx, edx; dwFlags
0x180007bf6  mov     rcx, rax; hHeap
0x180007bf9  call    cs:__imp_HeapFree
0x180007bff  mov     rcx, cs:hLogHandle; hLogHandle
0x180007c06  call    cs:__imp_RouterLogDeregisterA
0x180007c0c  mov     dword ptr cs:qword_18002BD00, esi
0x180007c12  lea     rcx, Resource; Resource
0x180007c19  call    cs:__imp_RtlReleaseResource
0x180007c1f  mov     eax, ebx
0x180007c21  mov     rcx, [rbp+790h+var_30]
0x180007c28  xor     rcx, rsp; StackCookie
0x180007c2b  call    __security_check_cookie
0x180007c30  add     rsp, 878h
0x180007c37  pop     rdi
0x180007c38  pop     rsi
0x180007c39  pop     rbx
0x180007c3a  pop     rbp
0x180007c3b  retn
```
