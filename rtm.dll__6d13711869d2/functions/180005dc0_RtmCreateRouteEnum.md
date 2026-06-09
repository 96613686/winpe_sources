# RtmCreateRouteEnum

- ea: `0x180005dc0`
- end: `0x18000609a`
- name: `RtmCreateRouteEnum`
- size: `730`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_DEST_HANDLE DestHandle, RTM_VIEW_SET TargetViews, RTM_ENUM_FLAGS EnumFlags, PRTM_NET_ADDRESS StartDest, RTM_MATCH_FLAGS MatchingFlags, PRTM_ROUTE_INFO CriteriaRoute, ULONG CriteriaInterface, PRTM_ENUM_HANDLE RtmEnumHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008ebc`

## callees

- `0x180005a00`
- `0x180005dc0`
- `0x18001f946`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180005e85`
- `KERNEL32!HeapAlloc` at `0x180005f01`
- `KERNEL32!HeapAlloc` at `0x180005f95`
- `KERNEL32!HeapAlloc` at `0x180005e85`
- `KERNEL32!HeapAlloc` at `0x180005f01`
- `KERNEL32!HeapAlloc` at `0x180005f95`
- `KERNEL32!GetProcessHeap` at `0x180005e6f`
- `KERNEL32!GetProcessHeap` at `0x180005ef3`
- `KERNEL32!GetProcessHeap` at `0x180005f87`
- `KERNEL32!GetProcessHeap` at `0x18000601d`
- `KERNEL32!GetProcessHeap` at `0x180006049`
- `KERNEL32!GetProcessHeap` at `0x18000605d`
- `KERNEL32!GetProcessHeap` at `0x180005e6f`
- `KERNEL32!GetProcessHeap` at `0x180005ef3`
- `KERNEL32!GetProcessHeap` at `0x180005f87`
- `KERNEL32!GetProcessHeap` at `0x18000601d`
- `KERNEL32!GetProcessHeap` at `0x180006049`
- `KERNEL32!GetProcessHeap` at `0x18000605d`
- `KERNEL32!HeapFree` at `0x18000602b`
- `KERNEL32!HeapFree` at `0x180006057`
- `KERNEL32!HeapFree` at `0x18000606b`
- `KERNEL32!HeapFree` at `0x18000602b`
- `KERNEL32!HeapFree` at `0x180006057`
- `KERNEL32!HeapFree` at `0x18000606b`
- `KERNEL32!InitializeCriticalSection` at `0x180005f4d`
- `KERNEL32!InitializeCriticalSection` at `0x180005f4d`
- `KERNEL32!DeleteCriticalSection` at `0x18000603a`
- `KERNEL32!DeleteCriticalSection` at `0x18000603a`

## pseudocode

```c
DWORD __stdcall RtmCreateRouteEnum(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_DEST_HANDLE DestHandle,
        RTM_VIEW_SET TargetViews,
        RTM_ENUM_FLAGS EnumFlags,
        PRTM_NET_ADDRESS StartDest,
        RTM_MATCH_FLAGS MatchingFlags,
        PRTM_ROUTE_INFO CriteriaRoute,
        ULONG CriteriaInterface,
        PRTM_ENUM_HANDLE RtmEnumHandle)
{
  volatile signed __int32 *v9; // r14
  volatile signed __int32 *v10; // rbx
  HANDLE ProcessHeap; // rax
  DWORD DestEnum; // edi
  struct _RTL_CRITICAL_SECTION *v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rsi
  int v16; // r15d
  unsigned __int64 v17; // rcx
  unsigned int v18; // r13d
  HANDLE v19; // rax
  void *v20; // rax
  unsigned __int64 v21; // rcx
  unsigned int v22; // ebx
  HANDLE v23; // rax
  LPVOID v24; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  HANDLE LockSemaphore; // rbx
  HANDLE v28; // rax
  HANDLE v29; // rax
  _DWORD *v30; // [rsp+38h] [rbp-50h]

  v9 = (volatile signed __int32 *)((unsigned __int64)RtmRegHandle ^ 0x7754DF32);
  if ( (unsigned __int64)RtmRegHandle != 0x7754DF32
    && *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) != 1 )
  {
    v10 = 0;
    if ( !DestHandle )
      goto LABEL_8;
    if ( StartDest )
      return 87;
    v10 = (volatile signed __int32 *)((unsigned __int64)DestHandle ^ 0x7754DF32);
    if ( (unsigned __int64)DestHandle != 0x7754DF32
      && *(_WORD *)(((unsigned __int64)DestHandle ^ 0x7754DF32) + 0x6C) != 1 )
    {
LABEL_8:
      if ( (MatchingFlags & 0xFFFFFFEF) != 0 && !CriteriaRoute )
        return 87;
      v30 = *(_DWORD **)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x10);
      if ( (~v30[10] & TargetViews) != 0 )
        return 50;
      ProcessHeap = GetProcessHeap();
      DestEnum = 8;
      v14 = (struct _RTL_CRITICAL_SECTION *)HeapAlloc(ProcessHeap, 8u, 0x88u);
      v15 = v14;
      if ( !v14 )
        return DestEnum;
      v16 = 0;
      BYTE4(v14->DebugInfo) = 8;
      v14->LockCount = TargetViews;
      v14->RecursionCount = EnumFlags;
      if ( MatchingFlags )
      {
        LODWORD(v14->OwningThread) = MatchingFlags;
        if ( (MatchingFlags & 0xFFFFFFEF) != 0 )
        {
          v17 = 8LL * (unsigned int)(v30[77] - 1);
          if ( v17 > 0xFFFFFFFF || (int)v17 + 64 < (unsigned int)v17 )
            goto LABEL_22;
          v18 = v17 + 64;
          v19 = GetProcessHeap();
          v20 = HeapAlloc(v19, 0, v18);
          v15->LockSemaphore = v20;
          if ( !v20 )
          {
            DestEnum = 31;
            goto LABEL_31;
          }
          memcpy_0(v20, CriteriaRoute, v18);
        }
        LODWORD(v15->SpinCount) = CriteriaInterface;
      }
      InitializeCriticalSection(v15 + 1);
      v16 = 1;
      if ( DestHandle )
      {
        v15[2].LockSemaphore = (HANDLE)v10;
        _InterlockedIncrement(v10);
LABEL_30:
        _InterlockedIncrement(v9);
        *RtmEnumHandle = (HANDLE)((unsigned __int64)v15 ^ 0x7754DF32);
        return 0;
      }
      v21 = 40LL * (unsigned int)v30[11];
      if ( v21 <= 0xFFFFFFFF && (int)v21 + 48 >= (unsigned int)v21 )
      {
        v22 = v21 + 48;
        v23 = GetProcessHeap();
        v24 = HeapAlloc(v23, 8u, v22);
        *(_QWORD *)&v15[2].LockCount = v24;
        if ( v24 )
        {
          DestEnum = RtmCreateDestEnum(
                       RtmRegHandle,
                       TargetViews,
                       EnumFlags,
                       StartDest,
                       0,
                       (PRTM_ENUM_HANDLE)&v15[2].DebugInfo);
          if ( !DestEnum )
            goto LABEL_30;
        }
LABEL_31:
        v25 = *(void **)&v15[2].LockCount;
        if ( v25 )
        {
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v25);
        }
        if ( v16 )
          DeleteCriticalSection(v15 + 1);
        LockSemaphore = v15->LockSemaphore;
        if ( LockSemaphore )
        {
          v28 = GetProcessHeap();
          HeapFree(v28, 0, LockSemaphore);
        }
        v29 = GetProcessHeap();
        HeapFree(v29, 0, v15);
        *RtmEnumHandle = 0;
        return DestEnum;
      }
LABEL_22:
      DestEnum = 534;
      goto LABEL_31;
    }
  }
  return 6;
}

```

## disassembly

```asm
0x180005dc0  mov     rax, rsp
0x180005dc3  mov     [rax+20h], r9d
0x180005dc7  mov     [rax+18h], r8d
0x180005dcb  mov     [rax+10h], rdx
0x180005dcf  mov     [rax+8], rcx
0x180005dd3  push    rbx
0x180005dd4  push    rsi
0x180005dd5  push    rdi
0x180005dd6  push    r12
0x180005dd8  push    r13
0x180005dda  push    r14
0x180005ddc  push    r15
0x180005dde  sub     rsp, 50h
0x180005de2  mov     rax, rdx
0x180005de5  mov     r14, rcx
0x180005de8  mov     edx, 7754DF32h
0x180005ded  xor     r14, rdx
0x180005df0  jz      loc_180006085
0x180005df6  mov     ecx, 1
0x180005dfb  cmp     [r14+30h], ecx
0x180005dff  jz      loc_180006085
0x180005e05  xor     ebx, ebx
0x180005e07  test    rax, rax
0x180005e0a  jz      short loc_180005E2C
0x180005e0c  cmp     [rsp+88h+StartDest], rbx
0x180005e14  jnz     short loc_180005E48
0x180005e16  mov     rbx, rax
0x180005e19  xor     rbx, rdx
0x180005e1c  jz      loc_180006085
0x180005e22  cmp     [rbx+6Ch], cx
0x180005e26  jz      loc_180006085
0x180005e2c  mov     r13d, [rsp+88h+MatchingFlags]
0x180005e34  mov     r12d, r13d
0x180005e37  and     r12d, 0FFFFFFEFh
0x180005e3b  jz      short loc_180005E52
0x180005e3d  cmp     [rsp+88h+CriteriaRoute], 0
0x180005e46  jnz     short loc_180005E52
0x180005e48  mov     eax, 57h ; 'W'
0x180005e4d  jmp     loc_18000608A
0x180005e52  mov     rax, [r14+10h]
0x180005e56  mov     [rsp+88h+var_50], rax
0x180005e5b  mov     eax, [rax+28h]
0x180005e5e  not     eax
0x180005e60  test    r8d, eax
0x180005e63  jz      short loc_180005E6F
0x180005e65  mov     eax, 32h ; '2'
0x180005e6a  jmp     loc_18000608A
0x180005e6f  call    cs:__imp_GetProcessHeap
0x180005e75  mov     rcx, rax; hHeap
0x180005e78  mov     edi, 8
0x180005e7d  mov     r8d, 88h; dwBytes
0x180005e83  mov     edx, edi; dwFlags
0x180005e85  call    cs:__imp_HeapAlloc
0x180005e8b  mov     rsi, rax
0x180005e8e  mov     [rsp+88h+var_48], rax
0x180005e93  test    rax, rax
0x180005e96  jnz     short loc_180005E9F
0x180005e98  mov     eax, edi
0x180005e9a  jmp     loc_18000608A
0x180005e9f  xor     r15d, r15d
0x180005ea2  mov     [rsp+88h+var_58], r15d
0x180005ea7  mov     [rax+4], dil
0x180005eab  mov     eax, [rsp+88h+TargetViews]
0x180005eb2  mov     [rsi+8], eax
0x180005eb5  mov     eax, [rsp+88h+EnumFlags]
0x180005ebc  mov     [rsi+0Ch], eax
0x180005ebf  test    r13d, r13d
0x180005ec2  jz      short loc_180005F43
0x180005ec4  mov     [rsi+10h], r13d
0x180005ec8  test    r12d, r12d
0x180005ecb  mov     r12d, 0FFFFFFFFh
0x180005ed1  jz      short loc_180005F23
0x180005ed3  mov     rax, [rsp+88h+var_50]
0x180005ed8  mov     ecx, [rax+134h]
0x180005ede  dec     ecx
0x180005ee0  shl     rcx, 3
0x180005ee4  cmp     rcx, r12
0x180005ee7  ja      short loc_180005F39
0x180005ee9  lea     eax, [rcx+40h]
0x180005eec  cmp     eax, ecx
0x180005eee  jb      short loc_180005F39
0x180005ef0  mov     r13d, eax
0x180005ef3  call    cs:__imp_GetProcessHeap
0x180005ef9  mov     rcx, rax; hHeap
0x180005efc  mov     r8d, r13d; dwBytes
0x180005eff  xor     edx, edx; dwFlags
0x180005f01  call    cs:__imp_HeapAlloc
0x180005f07  mov     [rsi+18h], rax
0x180005f0b  test    rax, rax
0x180005f0e  jz      short loc_180005F2F
0x180005f10  mov     r8d, r13d; Size
0x180005f13  mov     rdx, [rsp+88h+CriteriaRoute]; Src
0x180005f1b  mov     rcx, rax; void *
0x180005f1e  call    memcpy_0
0x180005f23  mov     eax, [rsp+88h+CriteriaInterface]
0x180005f2a  mov     [rsi+20h], eax
0x180005f2d  jmp     short loc_180005F49
0x180005f2f  mov     edi, 1Fh
0x180005f34  jmp     loc_180006014
0x180005f39  mov     edi, 216h
0x180005f3e  jmp     loc_180006014
0x180005f43  mov     r12d, 0FFFFFFFFh
0x180005f49  lea     rcx, [rsi+28h]; lpCriticalSection
0x180005f4d  call    cs:__imp_InitializeCriticalSection
0x180005f53  mov     r15d, 1
0x180005f59  mov     [rsp+88h+var_58], r15d
0x180005f5e  cmp     [rsp+88h+arg_8], 0
0x180005f67  jnz     short loc_180005FE1
0x180005f69  mov     rax, [rsp+88h+var_50]
0x180005f6e  mov     eax, [rax+2Ch]
0x180005f71  lea     rcx, [rax+rax*4]
0x180005f75  shl     rcx, 3
0x180005f79  cmp     rcx, r12
0x180005f7c  ja      short loc_180005F39
0x180005f7e  lea     eax, [rcx+30h]
0x180005f81  cmp     eax, ecx
0x180005f83  jb      short loc_180005F39
0x180005f85  mov     ebx, eax
0x180005f87  call    cs:__imp_GetProcessHeap
0x180005f8d  mov     rcx, rax; hHeap
0x180005f90  mov     r8d, ebx; dwBytes
0x180005f93  mov     edx, edi; dwFlags
0x180005f95  call    cs:__imp_HeapAlloc
0x180005f9b  mov     [rsi+58h], rax
0x180005f9f  test    rax, rax
0x180005fa2  jz      short loc_180006014
0x180005fa4  lea     rax, [rsi+50h]
0x180005fa8  mov     [rsp+88h+var_60], rax; RtmEnumHandle
0x180005fad  mov     [rsp+88h+ProtocolId], 0; ProtocolId
0x180005fb5  mov     r9, [rsp+88h+StartDest]; NetAddress
0x180005fbd  mov     r8d, [rsp+88h+EnumFlags]; EnumFlags
0x180005fc5  mov     edx, [rsp+88h+TargetViews]; TargetViews
0x180005fcc  mov     rcx, [rsp+88h+RtmRegHandle]; RtmRegHandle
0x180005fd4  call    RtmCreateDestEnum
0x180005fd9  mov     edi, eax
0x180005fdb  test    eax, eax
0x180005fdd  jnz     short loc_180006014
0x180005fdf  jmp     short loc_180005FE8
0x180005fe1  mov     [rsi+68h], rbx
0x180005fe5  lock inc dword ptr [rbx]
0x180005fe8  lock inc dword ptr [r14]
0x180005fec  xor     rsi, 7754DF32h
0x180005ff3  mov     rax, [rsp+88h+RtmEnumHandle]
0x180005ffb  mov     [rax], rsi
0x180005ffe  xor     eax, eax
0x180006000  jmp     loc_18000608A
0x180006005  mov     edi, 8
0x18000600a  mov     rsi, [rsp+88h+var_48]
0x18000600f  mov     r15d, [rsp+88h+var_58]
0x180006014  mov     rbx, [rsi+58h]
0x180006018  test    rbx, rbx
0x18000601b  jz      short loc_180006031
0x18000601d  call    cs:__imp_GetProcessHeap
0x180006023  mov     rcx, rax; hHeap
0x180006026  mov     r8, rbx; lpMem
0x180006029  xor     edx, edx; dwFlags
0x18000602b  call    cs:__imp_HeapFree
0x180006031  test    r15d, r15d
0x180006034  jz      short loc_180006040
0x180006036  lea     rcx, [rsi+28h]; lpCriticalSection
0x18000603a  call    cs:__imp_DeleteCriticalSection
0x180006040  mov     rbx, [rsi+18h]
0x180006044  test    rbx, rbx
0x180006047  jz      short loc_18000605D
0x180006049  call    cs:__imp_GetProcessHeap
0x18000604f  mov     rcx, rax; hHeap
0x180006052  mov     r8, rbx; lpMem
0x180006055  xor     edx, edx; dwFlags
0x180006057  call    cs:__imp_HeapFree
0x18000605d  call    cs:__imp_GetProcessHeap
0x180006063  mov     rcx, rax; hHeap
0x180006066  mov     r8, rsi; lpMem
0x180006069  xor     edx, edx; dwFlags
0x18000606b  call    cs:__imp_HeapFree
0x180006071  mov     rax, [rsp+88h+RtmEnumHandle]
0x180006079  mov     qword ptr [rax], 0
0x180006080  jmp     loc_180005E98
0x180006085  mov     eax, 6
0x18000608a  add     rsp, 50h
0x18000608e  pop     r15
0x180006090  pop     r14
0x180006092  pop     r13
0x180006094  pop     r12
0x180006096  pop     rdi
0x180006097  pop     rsi
0x180006098  pop     rbx
0x180006099  retn
```
