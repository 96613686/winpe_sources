# SslInitContextManager(void)

- ea: `0x180022570`
- end: `0x180022831`
- name: `?SslInitContextManager@@YAHXZ`
- size: `705`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180047bc0`

## callees

- `0x180014240`
- `0x180021eb0`
- `0x180022570`
- `0x180057c8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022758`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022758`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800225ce`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800225ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022703`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022749`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022703`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022749`
- `ntdll!RtlDeleteResource` at `0x18008c63d`
- `ntdll!RtlDeleteResource` at `0x18008c63d`
- `ntdll!RtlInitializeResource` at `0x180022621`
- `ntdll!RtlInitializeResource` at `0x180022621`

## string_xrefs

- `0x1800225c0`: `System\CurrentControlSet\Control\SecurityProviders\Schannel`

## pseudocode

```c
__int64 SslInitContextManager(void)
{
  unsigned int v0; // ebx
  DWORD v1; // edi
  struct _LIST_ENTRY *v2; // rax
  struct _LIST_ENTRY *v3; // rdx
  unsigned int v4; // r8d
  struct _LIST_ENTRY *v5; // rcx
  unsigned __int8 v6; // si
  DWORD i; // r14d
  DWORD dwDisposition; // [rsp+50h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-30h] BYREF
  DWORD Type; // [rsp+90h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int v14; // [rsp+A8h] [rbp+20h] BYREF

  v0 = 0;
  hKey = 0;
  dwDisposition = 0;
  if ( !dword_1800AE790 )
  {
    if ( !RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\SecurityProviders\\Schannel",
            0,
            (LPWSTR)&Class,
            0,
            0x20019u,
            0,
            &hKey,
            &dwDisposition) )
    {
      Type = 0;
      v14 = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UserContextLockCount", 0, &Type, (LPBYTE)&Data, &cbData)
        && Type == 4
        && Data - 1 <= 0x1FF
        && ((Data - 1) & Data) == 0 )
      {
        dwSslContextLockCount = Data;
      }
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"UserContextListCount", 0, &Type, (LPBYTE)&v14, &cbData)
        && Type == 4
        && v14
        && ((v14 - 1) & v14) == 0 )
      {
        dwSslContextListCount = v14;
      }
      RegCloseKey(hKey);
      hKey = 0;
    }
    SslContextLock = SPExternalAlloc(96 * dwSslContextLockCount);
    v1 = 0;
    if ( SslContextLock )
    {
      while ( 1 )
      {
        Type = v1;
        if ( v1 >= dwSslContextLockCount )
          break;
        RtlInitializeResource((PRTL_RESOURCE)SslContextLock + v1++);
      }
      v2 = (struct _LIST_ENTRY *)SPExternalAlloc(16 * dwSslContextListCount);
      v3 = v2;
      SslContextList = v2;
      if ( v2 )
      {
        v4 = dwSslContextListCount;
        if ( dwSslContextListCount )
        {
          do
          {
            v5 = &v2[v0];
            v5->Blink = v5;
            v5->Flink = v5;
            ++v0;
          }
          while ( v0 < v4 );
        }
        dword_1800AE790 = 1;
        return 1;
      }
    }
    else
    {
      v3 = SslContextList;
    }
    v6 = 0;
    if ( v3 )
    {
      SPExternalFree(v3);
      SslContextList = 0;
    }
    if ( SslContextLock )
    {
      for ( i = 0; i < v1; ++i )
        RtlDeleteResource((PRTL_RESOURCE)SslContextLock + i);
      SPExternalFree(SslContextLock);
      SslContextLock = 0;
    }
    return v6;
  }
  return 1;
}

```

## disassembly

```asm
0x180022570  push    rbx
0x180022572  push    rsi
0x180022573  push    rdi
0x180022574  push    r14
0x180022576  sub     rsp, 68h
0x18002257a  xor     ebx, ebx
0x18002257c  mov     [rsp+88h+hKey], rbx
0x180022581  mov     [rsp+88h+dwDisposition], ebx
0x180022585  cmp     cs:dword_1800AE790, ebx
0x18002258b  jnz     loc_180022768
0x180022591  lea     rax, [rsp+88h+dwDisposition]
0x180022596  mov     [rsp+88h+lpdwDisposition], rax; lpdwDisposition
0x18002259b  lea     rax, [rsp+88h+hKey]
0x1800225a0  mov     [rsp+88h+phkResult], rax; phkResult
0x1800225a5  mov     [rsp+88h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800225aa  mov     [rsp+88h+samDesired], 20019h; samDesired
0x1800225b2  mov     [rsp+88h+dwOptions], ebx; dwOptions
0x1800225b6  lea     r9, Class; lpClass
0x1800225bd  xor     r8d, r8d; Reserved
0x1800225c0  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Sec"...
0x1800225c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800225ce  call    cs:__imp_RegCreateKeyExW
0x1800225d4  test    eax, eax
0x1800225d6  jz      loc_1800226B2
0x1800225dc  mov     eax, cs:?dwSslContextLockCount@@3KA; ulong dwSslContextLockCount
0x1800225e2  lea     ecx, [rax+rax*2]
0x1800225e5  shl     ecx, 5; uBytes
0x1800225e8  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x1800225ed  mov     cs:?SslContextLock@@3PEAU_RTL_RESOURCE@@EA, rax; _RTL_RESOURCE * SslContextLock
0x1800225f4  mov     edi, ebx
0x1800225f6  test    rax, rax
0x1800225f9  jz      loc_1800227CE
0x1800225ff  mov     esi, ebx
0x180022601  mov     [rsp+88h+Type], edi
0x180022608  cmp     edi, cs:?dwSslContextLockCount@@3KA; ulong dwSslContextLockCount
0x18002260e  jnb     short loc_18002263D
0x180022610  mov     eax, edi
0x180022612  lea     rcx, [rax+rax*2]
0x180022616  shl     rcx, 5
0x18002261a  add     rcx, cs:?SslContextLock@@3PEAU_RTL_RESOURCE@@EA; Resource
0x180022621  call    cs:__imp_RtlInitializeResource
0x180022627  jmp     short loc_180022639
0x180022629  mov     esi, 0C000009Ah
0x18002262e  xor     ebx, ebx
0x180022630  mov     edi, [rsp+88h+Type]
0x180022637  jmp     short loc_18002263D
0x180022639  inc     edi
0x18002263b  jmp     short loc_180022601
0x18002263d  test    esi, esi
0x18002263f  js      loc_1800227F5
0x180022645  mov     ecx, cs:?dwSslContextListCount@@3KA; ulong dwSslContextListCount
0x18002264b  shl     ecx, 4; uBytes
0x18002264e  call    ?SPExternalAlloc@@YAPEAXK@Z; SPExternalAlloc(ulong)
0x180022653  mov     rdx, rax
0x180022656  mov     cs:?SslContextList@@3PEAU_LIST_ENTRY@@EA, rax; _LIST_ENTRY * SslContextList
0x18002265d  test    rax, rax
0x180022660  jz      loc_1800227D5
0x180022666  mov     r8d, cs:?dwSslContextListCount@@3KA; ulong dwSslContextListCount
0x18002266d  test    r8d, r8d
0x180022670  jz      short loc_180022697
0x180022672  nop     dword ptr [rax+00h]
0x180022676  nop     word ptr [rax+rax+00000000h]
0x180022680  mov     ecx, ebx
0x180022682  shl     rcx, 4
0x180022686  add     rcx, rax
0x180022689  mov     [rcx+8], rcx
0x18002268d  mov     [rcx], rcx
0x180022690  inc     ebx
0x180022692  cmp     ebx, r8d
0x180022695  jb      short loc_180022680
0x180022697  mov     cs:dword_1800AE790, 1
0x1800226a1  mov     sil, 1
0x1800226a4  movzx   eax, sil
0x1800226a8  add     rsp, 68h
0x1800226ac  pop     r14
0x1800226ae  pop     rdi
0x1800226af  pop     rsi
0x1800226b0  pop     rbx
0x1800226b1  retn
0x1800226b2  mov     [rsp+88h+Type], ebx
0x1800226b9  mov     [rsp+88h+arg_18], ebx
0x1800226c0  mov     [rsp+88h+Data], ebx
0x1800226c7  mov     [rsp+88h+cbData], 4
0x1800226d2  lea     rax, [rsp+88h+cbData]
0x1800226da  mov     qword ptr [rsp+88h+samDesired], rax; lpcbData
0x1800226df  lea     rax, [rsp+88h+Data]
0x1800226e7  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x1800226ec  lea     r9, [rsp+88h+Type]; lpType
0x1800226f4  xor     r8d, r8d; lpReserved
0x1800226f7  lea     rdx, ValueName; "UserContextLockCount"
0x1800226fe  mov     rcx, [rsp+88h+hKey]; hKey
0x180022703  call    cs:__imp_RegQueryValueExW
0x180022709  test    eax, eax
0x18002270b  jz      short loc_180022777
0x18002270d  mov     [rsp+88h+cbData], 4
0x180022718  lea     rax, [rsp+88h+cbData]
0x180022720  mov     qword ptr [rsp+88h+samDesired], rax; lpcbData
0x180022725  lea     rax, [rsp+88h+arg_18]
0x18002272d  mov     qword ptr [rsp+88h+dwOptions], rax; lpData
0x180022732  lea     r9, [rsp+88h+Type]; lpType
0x18002273a  xor     r8d, r8d; lpReserved
0x18002273d  lea     rdx, aUsercontextlis; "UserContextListCount"
0x180022744  mov     rcx, [rsp+88h+hKey]; hKey
0x180022749  call    cs:__imp_RegQueryValueExW
0x18002274f  test    eax, eax
0x180022751  jz      short loc_1800227AA
0x180022753  mov     rcx, [rsp+88h+hKey]; hKey
0x180022758  call    cs:__imp_RegCloseKey
0x18002275e  mov     [rsp+88h+hKey], rbx
0x180022763  jmp     loc_1800225DC
0x180022768  mov     eax, 1
0x18002276d  add     rsp, 68h
0x180022771  pop     r14
0x180022773  pop     rdi
0x180022774  pop     rsi
0x180022775  pop     rbx
0x180022776  retn
0x180022777  cmp     [rsp+88h+Type], 4
0x18002277f  jnz     short loc_18002270D
0x180022781  mov     eax, [rsp+88h+Data]
0x180022788  lea     ecx, [rax-1]
0x18002278b  cmp     ecx, 1FFh
0x180022791  ja      loc_18002270D
0x180022797  test    eax, ecx
0x180022799  jnz     loc_18002270D
0x18002279f  mov     cs:?dwSslContextLockCount@@3KA, eax; ulong dwSslContextLockCount
0x1800227a5  jmp     loc_18002270D
0x1800227aa  cmp     [rsp+88h+Type], 4
0x1800227b2  jnz     short loc_180022753
0x1800227b4  mov     ecx, [rsp+88h+arg_18]
0x1800227bb  test    ecx, ecx
0x1800227bd  jz      short loc_180022753
0x1800227bf  lea     eax, [rcx-1]
0x1800227c2  test    ecx, eax
0x1800227c4  jnz     short loc_180022753
0x1800227c6  mov     cs:?dwSslContextListCount@@3KA, ecx; ulong dwSslContextListCount
0x1800227cc  jmp     short loc_180022753
0x1800227ce  mov     rdx, cs:?SslContextList@@3PEAU_LIST_ENTRY@@EA; _LIST_ENTRY * SslContextList
0x1800227d5  xor     sil, sil
0x1800227d8  test    rdx, rdx
0x1800227db  jz      loc_18008C616
0x1800227e1  mov     rcx, rdx; void *
0x1800227e4  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x1800227e9  mov     cs:?SslContextList@@3PEAU_LIST_ENTRY@@EA, rbx; _LIST_ENTRY * SslContextList
0x1800227f0  jmp     loc_18008C616
0x1800227f5  lea     rax, WPP_GLOBAL_Control
0x1800227fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022803  cmp     rcx, rax
0x180022806  jz      loc_18008C60A
0x18002280c  test    byte ptr [rcx+1Ch], 1
0x180022810  jz      loc_18008C60A
0x180022816  mov     edx, 0Ah
0x18002281b  lea     r8, WPP_bbe33ecd4d183e21185aee86644dce59_Traceguids
0x180022822  mov     rcx, [rcx+10h]
0x180022826  call    WPP_SF_
0x18002282b  nop
0x18002282c  jmp     loc_18008C60A
0x18008c60a  mov     rdx, cs:?SslContextList@@3PEAU_LIST_ENTRY@@EA; _LIST_ENTRY * SslContextList
0x18008c611  jmp     loc_1800227D5
0x18008c616  cmp     cs:?SslContextLock@@3PEAU_RTL_RESOURCE@@EA, 0; _RTL_RESOURCE * SslContextLock
0x18008c61e  jz      loc_1800226A4
0x18008c624  mov     r14d, ebx
0x18008c627  test    edi, edi
0x18008c629  jz      short loc_18008C64B
0x18008c62b  mov     eax, r14d
0x18008c62e  lea     rcx, [rax+rax*2]
0x18008c632  shl     rcx, 5
0x18008c636  add     rcx, cs:?SslContextLock@@3PEAU_RTL_RESOURCE@@EA; Resource
0x18008c63d  call    cs:__imp_RtlDeleteResource
0x18008c643  inc     r14d
0x18008c646  cmp     r14d, edi
0x18008c649  jb      short loc_18008C62B
0x18008c64b  mov     rcx, cs:?SslContextLock@@3PEAU_RTL_RESOURCE@@EA; void *
0x18008c652  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18008c657  mov     cs:?SslContextLock@@3PEAU_RTL_RESOURCE@@EA, rbx; _RTL_RESOURCE * SslContextLock
0x18008c65e  jmp     loc_1800226A4
```
