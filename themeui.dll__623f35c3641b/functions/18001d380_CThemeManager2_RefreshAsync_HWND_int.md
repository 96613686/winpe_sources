# CThemeManager2::RefreshAsync(HWND__ *,int)

- ea: `0x18001d380`
- end: `0x18001d47e`
- name: `?RefreshAsync@CThemeManager2@@UEAAJPEAUHWND__@@H@Z`
- size: `254`
- prototype: `__int64 __fastcall(PVOID pv, HWND, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18001d380`
- `0x18001d484`
- `0x18002033c`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d39e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d39e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d3bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d46b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d3bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d46b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d403`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001d403`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001d45e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001d45e`

## pseudocode

```c
__int64 __fastcall CThemeManager2::RefreshAsync(char *pv, HWND a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // edi
  PTP_WORK ThreadpoolWork; // rax
  __int64 v9; // rdx
  unsigned int (__fastcall *v10)(char *); // rax
  void (__fastcall *v11)(char *); // rax

  v3 = (struct _RTL_CRITICAL_SECTION *)(pv + 2168);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 2168));
  if ( !pv[2161] )
  {
    v7 = -2147467259;
    LeaveCriticalSection(v3);
    return v7;
  }
  pv[2161] = 0;
  LeaveCriticalSection(v3);
  if ( *((_QWORD *)pv + 264) )
    CDPA<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::DestroyCallback(pv + 2112);
  if ( (unsigned int)CDPA_Base<unsigned short,CTContainer_PolicyCoTaskMem>::Create(pv + 2112) )
  {
    if ( *((_QWORD *)pv + 269) )
    {
      v9 = *(_QWORD *)pv;
    }
    else
    {
      ThreadpoolWork = CreateThreadpoolWork(CThemeManager2::s_WorkCallback, pv, 0);
      v9 = *(_QWORD *)pv;
      *((_QWORD *)pv + 269) = ThreadpoolWork;
      if ( !ThreadpoolWork )
      {
        v10 = *(unsigned int (__fastcall **)(char *))(v9 + 40);
        pv[2161] = 1;
        return v10(pv);
      }
    }
    v11 = *(void (__fastcall **)(char *))(v9 + 8);
    v7 = 1;
    pv[2160] = 1;
    *((_DWORD *)pv + 552) = a3;
    *((_QWORD *)pv + 277) = a2;
    v11(pv);
    SubmitThreadpoolWork(*((PTP_WORK *)pv + 269));
    return v7;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18001d380  push    rbx
0x18001d382  push    rbp
0x18001d383  push    rsi
0x18001d384  push    rdi
0x18001d385  push    r14
0x18001d387  sub     rsp, 20h
0x18001d38b  lea     rsi, [rcx+878h]
0x18001d392  mov     rbx, rcx
0x18001d395  mov     rcx, rsi; lpCriticalSection
0x18001d398  mov     ebp, r8d
0x18001d39b  mov     r14, rdx
0x18001d39e  call    cs:__imp_EnterCriticalSection
0x18001d3a4  cmp     byte ptr [rbx+871h], 0
0x18001d3ab  mov     rcx, rsi; lpCriticalSection
0x18001d3ae  jz      loc_18001D466
0x18001d3b4  mov     byte ptr [rbx+871h], 0
0x18001d3bb  call    cs:__imp_LeaveCriticalSection
0x18001d3c1  lea     rdi, [rbx+840h]
0x18001d3c8  cmp     qword ptr [rdi], 0
0x18001d3cc  jz      short loc_18001D3D6
0x18001d3ce  mov     rcx, rdi
0x18001d3d1  call    ?DestroyCallback@?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAXP6AHPEAGPEAX@Z1@Z; CDPA<ushort,CTContainer_PolicyUnOwned<ushort>>::DestroyCallback(int (*)(ushort *,void *),void *)
0x18001d3d6  mov     rcx, rdi
0x18001d3d9  call    ?Create@?$CDPA_Base@GVCTContainer_PolicyCoTaskMem@@@@QEAAHH@Z; CDPA_Base<ushort,CTContainer_PolicyCoTaskMem>::Create(int)
0x18001d3de  test    eax, eax
0x18001d3e0  jnz     short loc_18001D3EC
0x18001d3e2  mov     edi, 8007000Eh
0x18001d3e7  jmp     loc_18001D471
0x18001d3ec  cmp     qword ptr [rbx+868h], 0
0x18001d3f4  jnz     short loc_18001D42F
0x18001d3f6  xor     r8d, r8d; pcbe
0x18001d3f9  lea     rcx, ?s_WorkCallback@CThemeManager2@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001d400  mov     rdx, rbx; pv
0x18001d403  call    cs:__imp_CreateThreadpoolWork
0x18001d409  mov     rdx, [rbx]
0x18001d40c  mov     [rbx+868h], rax
0x18001d413  test    rax, rax
0x18001d416  jnz     short loc_18001D432
0x18001d418  mov     rax, [rdx+28h]
0x18001d41c  mov     rcx, rbx
0x18001d41f  mov     byte ptr [rbx+871h], 1
0x18001d426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d42b  mov     edi, eax
0x18001d42d  jmp     short loc_18001D471
0x18001d42f  mov     rdx, [rbx]
0x18001d432  mov     rax, [rdx+8]
0x18001d436  mov     edi, 1
0x18001d43b  mov     rcx, rbx
0x18001d43e  mov     [rbx+870h], dil
0x18001d445  mov     [rbx+8A0h], ebp
0x18001d44b  mov     [rbx+8A8h], r14
0x18001d452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d457  mov     rcx, [rbx+868h]; pwk
0x18001d45e  call    cs:__imp_SubmitThreadpoolWork
0x18001d464  jmp     short loc_18001D471
0x18001d466  mov     edi, 80004005h
0x18001d46b  call    cs:__imp_LeaveCriticalSection
0x18001d471  mov     eax, edi
0x18001d473  add     rsp, 20h
0x18001d477  pop     r14
0x18001d479  pop     rdi
0x18001d47a  pop     rsi
0x18001d47b  pop     rbp
0x18001d47c  pop     rbx
0x18001d47d  retn
```
