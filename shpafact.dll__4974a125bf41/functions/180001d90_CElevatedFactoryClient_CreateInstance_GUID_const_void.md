# CElevatedFactoryClient::CreateInstance(_GUID const &,void * *)

- ea: `0x180001d90`
- end: `0x180001e46`
- name: `?CreateInstance@CElevatedFactoryClient@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `182`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002c00`

## callees

- `0x180001d90`
- `0x1800026d4`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001db6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001db6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001da4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001da4`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryClient::CreateInstance(const struct _GUID *a1, void **a2)
{
  int v4; // ebx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v6; // rax
  volatile signed __int32 *v7; // rdi

  v4 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v6 = (volatile signed __int32 *)HeapAlloc(ProcessHeap, 8u, 0x28u);
  v7 = v6;
  if ( !v6
    || (*(_QWORD *)v6 = &CElevatedFactoryClient::`vftable',
        *((_QWORD *)v6 + 3) = 0,
        _InterlockedIncrement(&g_cDllRefs),
        _InterlockedIncrement(v6 + 8),
        v4 = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))v6)((LPVOID)v6, a1, a2),
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7),
        v4 < 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids,
        (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001d90  push    rbx
0x180001d92  push    rbp
0x180001d93  push    rsi
0x180001d94  push    rdi
0x180001d95  sub     rsp, 28h
0x180001d99  mov     rsi, rdx
0x180001d9c  mov     rbp, rcx
0x180001d9f  mov     ebx, 8007000Eh
0x180001da4  call    cs:__imp_GetProcessHeap
0x180001daa  mov     edx, 8; dwFlags
0x180001daf  mov     rcx, rax; hHeap
0x180001db2  lea     r8d, [rdx+20h]; dwBytes
0x180001db6  call    cs:__imp_HeapAlloc
0x180001dbc  mov     rdi, rax
0x180001dbf  test    rax, rax
0x180001dc2  jz      short loc_180001E0A
0x180001dc4  lea     rax, ??_7CElevatedFactoryClient@@6B@; const CElevatedFactoryClient::`vftable'
0x180001dcb  mov     [rdi], rax
0x180001dce  mov     qword ptr [rdi+18h], 0
0x180001dd6  lock inc cs:?g_cDllRefs@@3JA; long g_cDllRefs
0x180001ddd  lock inc dword ptr [rdi+20h]
0x180001de1  mov     rax, [rdi]
0x180001de4  mov     r8, rsi
0x180001de7  mov     rdx, rbp
0x180001dea  mov     rcx, rdi
0x180001ded  mov     rax, [rax]
0x180001df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001df5  mov     rcx, [rdi]
0x180001df8  mov     ebx, eax
0x180001dfa  mov     rax, [rcx+10h]
0x180001dfe  mov     rcx, rdi
0x180001e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e06  test    ebx, ebx
0x180001e08  jns     short loc_180001E3B
0x180001e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e11  lea     rax, WPP_GLOBAL_Control
0x180001e18  cmp     rcx, rax
0x180001e1b  jz      short loc_180001E3B
0x180001e1d  test    byte ptr [rcx+1Ch], 4
0x180001e21  jz      short loc_180001E3B
0x180001e23  mov     rcx, [rcx+10h]
0x180001e27  lea     r8, WPP_0f628f1b17743b1a1d642676ad7906b4_Traceguids
0x180001e2e  mov     edx, 0Ah
0x180001e33  mov     r9d, ebx
0x180001e36  call    WPP_SF_d
0x180001e3b  mov     eax, ebx
0x180001e3d  add     rsp, 28h
0x180001e41  pop     rdi
0x180001e42  pop     rsi
0x180001e43  pop     rbp
0x180001e44  pop     rbx
0x180001e45  retn
```
