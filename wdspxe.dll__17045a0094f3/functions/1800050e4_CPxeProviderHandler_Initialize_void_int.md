# CPxeProviderHandler::Initialize(void *,int)

- ea: `0x1800050e4`
- end: `0x180005233`
- name: `?Initialize@CPxeProviderHandler@@QEAAKPEAXH@Z`
- size: `335`
- prototype: `unsigned int __fastcall(CPxeProviderHandler *__hidden this, void *, int)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002bc0`
- `0x180008a30`
- `0x180008aa0`
- `0x180008b80`
- `0x180008be0`
- `0x180008c30`
- `0x180008c90`
- `0x180008df0`

## callees

- `0x180005000`
- `0x1800050e4`
- `0x18000523c`
- `0x180005860`
- `0x1800070c8`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180005111`
- `KERNEL32!EnterCriticalSection` at `0x180005111`
- `KERNEL32!LeaveCriticalSection` at `0x180005209`
- `KERNEL32!LeaveCriticalSection` at `0x180005209`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180005155`
- `WdsCommonLib!?Initialize@CMRSWLock@@QEAAKK@Z` at `0x180005155`
- `WdsCommonLib!?Initialize@CBannedDeviceIds@@QEAAKPEBGPEAUHKEY__@@00@Z` at `0x1800051b7`
- `WdsCommonLib!?Initialize@CBannedDeviceIds@@QEAAKPEBGPEAUHKEY__@@00@Z` at `0x1800051b7`

## string_xrefs

- `0x1800051a9`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::Initialize(CPxeProviderHandler *this, void *a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  int v5; // ebx
  unsigned int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int ProvidersInfo; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  bool v23; // zf

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 336);
  v5 = 0;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  if ( *((_DWORD *)this + 94) )
    goto LABEL_9;
  v8 = CPool<PxeRequest>::Initialize((PSLIST_HEADER)this + 24);
  v7 = ElValidateWin32_2(v8, v9, v10, 637);
  if ( !v7 )
  {
    v11 = CMRSWLock::Initialize((CPxeProviderHandler *)((char *)this + 200), 0);
    v7 = ElValidateWin32_2(v11, v12, v13, 644);
    if ( !v7 )
    {
      ProvidersInfo = CPxeProviderHandler::LoadProvidersInfo(this);
      v7 = ElValidateWin32_2(ProvidersInfo, v15, v16, 651);
      if ( !v7 )
      {
        if ( a3 )
        {
LABEL_9:
          *((_DWORD *)this + 94) = 1;
          v23 = v7 == 0;
          goto LABEL_10;
        }
        v17 = CBannedDeviceIds::Initialize(
                (CPxeProviderHandler *)((char *)this + 136),
                0,
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE",
                L"BannedGuids");
        v7 = ElValidateWin32_2(v17, v18, v19, 666);
        if ( !v7 )
        {
          v20 = CPxeProviderHandler::InitializeProviders(this);
          v7 = ElValidateWin32_2(v20, v21, v22, 674);
        }
      }
    }
  }
  v23 = v7 == 0;
  if ( !v7 )
    goto LABEL_9;
LABEL_10:
  LOBYTE(v5) = !v23;
  *((_DWORD *)this + 81) = v5;
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x1800050e4  mov     rax, rsp
0x1800050e7  mov     [rax+8], rbx
0x1800050eb  mov     [rax+10h], rbp
0x1800050ef  mov     [rax+18h], rsi
0x1800050f3  mov     [rax+20h], rdi
0x1800050f7  push    r14
0x1800050f9  sub     rsp, 30h
0x1800050fd  lea     rbp, [rcx+150h]
0x180005104  mov     rsi, rcx
0x180005107  xor     ebx, ebx
0x180005109  mov     rcx, rbp; lpCriticalSection
0x18000510c  mov     r14d, r8d
0x18000510f  mov     edi, ebx
0x180005111  call    cs:__imp_EnterCriticalSection
0x180005118  nop     dword ptr [rax+rax+00h]
0x18000511d  cmp     [rsi+178h], ebx
0x180005123  jnz     loc_1800051F1
0x180005129  lea     rcx, [rsi+180h]; ListHead
0x180005130  call    ?Initialize@?$CPool@VPxeRequest@@@@QEAAKKK@Z; CPool<PxeRequest>::Initialize(ulong,ulong)
0x180005135  mov     ecx, eax
0x180005137  mov     r9d, 27Dh
0x18000513d  call    ElValidateWin32_2
0x180005142  mov     edi, eax
0x180005144  test    eax, eax
0x180005146  jnz     loc_1800051ED
0x18000514c  lea     rcx, [rsi+0C8h]
0x180005153  xor     edx, edx
0x180005155  call    cs:__imp_?Initialize@CMRSWLock@@QEAAKK@Z; CMRSWLock::Initialize(ulong)
0x18000515c  nop     dword ptr [rax+rax+00h]
0x180005161  mov     ecx, eax
0x180005163  mov     r9d, 284h
0x180005169  call    ElValidateWin32_2
0x18000516e  mov     edi, eax
0x180005170  test    eax, eax
0x180005172  jnz     short loc_1800051ED
0x180005174  mov     rcx, rsi; this
0x180005177  call    ?LoadProvidersInfo@CPxeProviderHandler@@AEAAKXZ; CPxeProviderHandler::LoadProvidersInfo(void)
0x18000517c  mov     ecx, eax
0x18000517e  mov     r9d, 28Bh
0x180005184  call    ElValidateWin32_2
0x180005189  mov     edi, eax
0x18000518b  test    eax, eax
0x18000518d  jnz     short loc_1800051ED
0x18000518f  test    r14d, r14d
0x180005192  jnz     short loc_1800051F1
0x180005194  lea     rax, aBannedguids; "BannedGuids"
0x18000519b  xor     edx, edx
0x18000519d  lea     rcx, [rsi+88h]
0x1800051a4  mov     [rsp+38h+var_18], rax
0x1800051a9  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\WD"...
0x1800051b0  mov     r8, 0FFFFFFFF80000002h
0x1800051b7  call    cs:__imp_?Initialize@CBannedDeviceIds@@QEAAKPEBGPEAUHKEY__@@00@Z; CBannedDeviceIds::Initialize(ushort const *,HKEY__ *,ushort const *,ushort const *)
0x1800051be  nop     dword ptr [rax+rax+00h]
0x1800051c3  mov     ecx, eax
0x1800051c5  mov     r9d, 29Ah
0x1800051cb  call    ElValidateWin32_2
0x1800051d0  mov     edi, eax
0x1800051d2  test    eax, eax
0x1800051d4  jnz     short loc_1800051ED
0x1800051d6  mov     rcx, rsi; this
0x1800051d9  call    ?InitializeProviders@CPxeProviderHandler@@AEAAKXZ; CPxeProviderHandler::InitializeProviders(void)
0x1800051de  mov     ecx, eax
0x1800051e0  mov     r9d, 2A2h
0x1800051e6  call    ElValidateWin32_2
0x1800051eb  mov     edi, eax
0x1800051ed  test    edi, edi
0x1800051ef  jnz     short loc_1800051FD
0x1800051f1  mov     dword ptr [rsi+178h], 1
0x1800051fb  test    edi, edi
0x1800051fd  setnz   bl
0x180005200  mov     rcx, rbp; lpCriticalSection
0x180005203  mov     [rsi+144h], ebx
0x180005209  call    cs:__imp_LeaveCriticalSection
0x180005210  nop     dword ptr [rax+rax+00h]
0x180005215  mov     rbx, [rsp+38h+arg_0]
0x18000521a  mov     eax, edi
0x18000521c  mov     rdi, [rsp+38h+arg_18]
0x180005221  mov     rbp, [rsp+38h+arg_8]
0x180005226  mov     rsi, [rsp+38h+arg_10]
0x18000522b  add     rsp, 30h
0x18000522f  pop     r14
0x180005231  retn
```
