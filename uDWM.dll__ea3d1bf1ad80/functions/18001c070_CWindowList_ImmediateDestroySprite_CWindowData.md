# CWindowList::ImmediateDestroySprite(CWindowData *)

- ea: `0x18001c070`
- end: `0x18001c2a1`
- name: `?ImmediateDestroySprite@CWindowList@@AEAAXPEAVCWindowData@@@Z`
- size: `561`
- prototype: `void __fastcall(CWindowList *__hidden this, struct CWindowData *)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c000`
- `0x18003b0c0`
- `0x1800466f0`
- `0x1800dae54`

## callees

- `0x1800191a0`
- `0x18001a0fc`
- `0x18001a180`
- `0x18001a2fc`
- `0x18001a314`
- `0x18001c070`
- `0x18001c2a8`
- `0x18001c5c0`
- `0x18004769c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001c296`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001c296`
- `ntdll!RtlLookupElementGenericTable` at `0x18001c11e`
- `ntdll!RtlLookupElementGenericTable` at `0x18001c214`
- `ntdll!RtlLookupElementGenericTable` at `0x18001c11e`
- `ntdll!RtlLookupElementGenericTable` at `0x18001c214`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001c137`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001c137`

## pseudocode

```c
void __fastcall CWindowList::ImmediateDestroySprite(CWindowList *this, struct CWindowData *a2)
{
  __int64 v4; // rcx
  unsigned int v5; // edx
  __int64 v6; // r8
  __int64 v7; // rdx
  struct CWindowData *v8; // rax
  struct CWindowData **v9; // rcx
  char v10; // r14
  char v11; // r14
  __int64 *v12; // rax
  CTopLevelWindow *v13; // rcx
  char v14; // si
  CVisual *v15; // rcx
  CVisual *v16; // rcx
  _QWORD *v17; // rax
  _QWORD v18[2]; // [rsp+20h] [rbp-60h] BYREF
  __int128 v19; // [rsp+30h] [rbp-50h]
  __int128 v20; // [rsp+40h] [rbp-40h]
  __int128 v21; // [rsp+50h] [rbp-30h]
  __int64 v22; // [rsp+60h] [rbp-20h]
  char v23; // [rsp+68h] [rbp-18h]
  __int128 v24; // [rsp+70h] [rbp-10h]
  struct CWindowData *Buffer; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+28h] BYREF

  v4 = 0;
  v5 = *((_DWORD *)this + 76);
  v6 = *((_QWORD *)this + 35);
  if ( v5 )
  {
    do
    {
      if ( a2 == *(struct CWindowData **)(v6 + 8 * v4) )
        break;
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (unsigned int)v4 < v5 );
  }
  if ( (unsigned int)v4 < v5 )
  {
    if ( (unsigned int)v4 < v5 - 1 )
    {
      do
      {
        v7 = (unsigned int)(v4 + 1);
        *(_QWORD *)(v6 + 8 * v4) = *(_QWORD *)(v6 + 8 * v7);
        v4 = v7;
      }
      while ( (unsigned int)v7 < *((_DWORD *)this + 76) - 1 );
    }
    --*((_DWORD *)this + 76);
  }
  v8 = *(struct CWindowData **)a2;
  if ( *(struct CWindowData **)(*(_QWORD *)a2 + 8LL) != a2
    || (v9 = (struct CWindowData **)*((_QWORD *)a2 + 1), *v9 != a2) )
  {
    __fastfail(3u);
  }
  *v9 = v8;
  *((_QWORD *)v8 + 1) = v9;
  v10 = *((_BYTE *)a2 + 736);
  *((_QWORD *)a2 + 1) = a2;
  *(_QWORD *)a2 = a2;
  v11 = v10 & 4;
  if ( v11 )
  {
    Buffer = a2;
    v12 = (__int64 *)RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 312), &Buffer);
    if ( v12 )
    {
      v26 = *v12;
      if ( !RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 312), &v26) )
        RaiseFailFastException(0, 0, 1u);
    }
    *((_BYTE *)a2 + 736) &= ~4u;
  }
  v13 = (CTopLevelWindow *)*((_QWORD *)a2 + 55);
  if ( v13 )
    CTopLevelWindow::ForceShowWindow(v13, 0);
  v14 = *((_BYTE *)a2 + 736);
  *((_QWORD *)a2 + 4) = 0;
  *((_BYTE *)a2 + 736) = v14 & 0xFE;
  if ( !*((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 20) )
  {
    CWindowList::CheckForMaximizedChange(this, a2);
    if ( (v14 & 1) != 0 )
    {
      if ( *((_DWORD *)a2 + 32) == 1 || !v11 )
        CWindowList::ShowHide(this, a2, 1);
    }
    else
    {
      CWindowData::OnVisibilityUpdated(a2);
    }
  }
  v15 = (CVisual *)*((_QWORD *)a2 + 56);
  if ( v15 )
    CVisual::RemoveSelfFromParent(v15);
  v16 = (CVisual *)*((_QWORD *)a2 + 55);
  if ( v16 )
    CVisual::RemoveSelfFromParent(v16);
  *((_BYTE *)a2 + 737) &= ~0x20u;
  CWindowList::OnGDISurfaceChange(v16, a2);
  v18[0] = *((_QWORD *)a2 + 17);
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v24 = 0;
  v18[1] = 0;
  v22 = -1;
  v23 = 0;
  v17 = RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 8), v18);
  if ( v17 )
    v17 = (_QWORD *)v17[8];
  if ( *((_QWORD **)a2 + 5) == v17 )
    CWindowList::UpdateDesktopWindowReplacement(this, *((_QWORD *)a2 + 17));
  if ( !*((_QWORD *)a2 + 3) )
    CWindowList::ImmediateDestroyWindow(this, a2);
}

```

## disassembly

```asm
0x18001c070  mov     [rsp-18h+arg_10], rbx
0x18001c075  mov     [rsp-18h+arg_18], rsi
0x18001c07a  push    rbp
0x18001c07b  push    rdi
0x18001c07c  push    r14
0x18001c07e  mov     rbp, rsp
0x18001c081  sub     rsp, 80h
0x18001c088  mov     rdi, rcx
0x18001c08b  mov     rbx, rdx
0x18001c08e  xor     ecx, ecx
0x18001c090  mov     edx, [rdi+130h]
0x18001c096  mov     r8, [rdi+118h]
0x18001c09d  test    edx, edx
0x18001c09f  jz      short loc_18001C0AD
0x18001c0a1  cmp     rbx, [r8+rcx*8]
0x18001c0a5  jz      short loc_18001C0AD
0x18001c0a7  inc     ecx
0x18001c0a9  cmp     ecx, edx
0x18001c0ab  jb      short loc_18001C0A1
0x18001c0ad  cmp     ecx, edx
0x18001c0af  jnb     short loc_18001C0D7
0x18001c0b1  lea     eax, [rdx-1]
0x18001c0b4  cmp     ecx, eax
0x18001c0b6  jnb     short loc_18001C0D1
0x18001c0b8  lea     edx, [rcx+1]
0x18001c0bb  mov     rax, [r8+rdx*8]
0x18001c0bf  mov     [r8+rcx*8], rax
0x18001c0c3  mov     eax, [rdi+130h]
0x18001c0c9  dec     eax
0x18001c0cb  mov     ecx, edx
0x18001c0cd  cmp     edx, eax
0x18001c0cf  jb      short loc_18001C0B8
0x18001c0d1  dec     dword ptr [rdi+130h]
0x18001c0d7  mov     rax, [rbx]
0x18001c0da  cmp     [rax+8], rbx
0x18001c0de  jnz     loc_18001C287
0x18001c0e4  mov     rcx, [rbx+8]
0x18001c0e8  cmp     [rcx], rbx
0x18001c0eb  jnz     loc_18001C287
0x18001c0f1  mov     [rcx], rax
0x18001c0f4  mov     [rax+8], rcx
0x18001c0f8  mov     r14b, [rbx+2E0h]
0x18001c0ff  mov     [rbx+8], rbx
0x18001c103  mov     [rbx], rbx
0x18001c106  and     r14b, 4
0x18001c10a  jz      short loc_18001C14C
0x18001c10c  lea     rsi, [rdi+138h]
0x18001c113  mov     [rbp+Buffer], rbx
0x18001c117  mov     rcx, rsi; Table
0x18001c11a  lea     rdx, [rbp+Buffer]; Buffer
0x18001c11e  call    cs:__imp_RtlLookupElementGenericTable
0x18001c124  test    rax, rax
0x18001c127  jz      short loc_18001C145
0x18001c129  mov     rax, [rax]
0x18001c12c  lea     rdx, [rbp+arg_8]; Buffer
0x18001c130  mov     rcx, rsi; Table
0x18001c133  mov     [rbp+arg_8], rax
0x18001c137  call    cs:__imp_RtlDeleteElementGenericTable
0x18001c13d  test    al, al
0x18001c13f  jz      loc_18001C28E
0x18001c145  and     byte ptr [rbx+2E0h], 0FBh
0x18001c14c  mov     rcx, [rbx+1B8h]; this
0x18001c153  test    rcx, rcx
0x18001c156  jz      short loc_18001C15F
0x18001c158  xor     edx, edx; bool
0x18001c15a  call    ?ForceShowWindow@CTopLevelWindow@@QEAAX_N@Z; CTopLevelWindow::ForceShowWindow(bool)
0x18001c15f  mov     sil, [rbx+2E0h]
0x18001c166  mov     al, sil
0x18001c169  mov     qword ptr [rbx+20h], 0
0x18001c171  and     al, 0FEh
0x18001c173  mov     [rbx+2E0h], al
0x18001c179  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001c180  cmp     byte ptr [rax+14h], 0
0x18001c184  jnz     short loc_18001C1A3
0x18001c186  mov     rdx, rbx; struct CWindowData *
0x18001c189  mov     rcx, rdi; this
0x18001c18c  call    ?CheckForMaximizedChange@CWindowList@@AEAAXPEAVCWindowData@@@Z; CWindowList::CheckForMaximizedChange(CWindowData *)
0x18001c191  test    sil, 1
0x18001c195  jnz     loc_18001C262
0x18001c19b  mov     rcx, rbx; this
0x18001c19e  call    ?OnVisibilityUpdated@CWindowData@@QEAAJXZ; CWindowData::OnVisibilityUpdated(void)
0x18001c1a3  mov     rcx, [rbx+1C0h]; this
0x18001c1aa  test    rcx, rcx
0x18001c1ad  jz      short loc_18001C1B4
0x18001c1af  call    ?RemoveSelfFromParent@CVisual@@QEAAJXZ; CVisual::RemoveSelfFromParent(void)
0x18001c1b4  mov     rcx, [rbx+1B8h]; this
0x18001c1bb  test    rcx, rcx
0x18001c1be  jz      short loc_18001C1C5
0x18001c1c0  call    ?RemoveSelfFromParent@CVisual@@QEAAJXZ; CVisual::RemoveSelfFromParent(void)
0x18001c1c5  and     byte ptr [rbx+2E1h], 0DFh
0x18001c1cc  mov     rdx, rbx; struct CWindowData *
0x18001c1cf  call    ?OnGDISurfaceChange@CWindowList@@AEAAXPEAVCWindowData@@@Z; CWindowList::OnGDISurfaceChange(CWindowData *)
0x18001c1d4  mov     rax, [rbx+88h]
0x18001c1db  lea     rcx, [rdi+8]; Table
0x18001c1df  xorps   xmm0, xmm0
0x18001c1e2  mov     [rbp+var_60], rax
0x18001c1e6  xorps   xmm1, xmm1
0x18001c1e9  movdqa  [rbp+var_50], xmm0
0x18001c1ee  lea     rdx, [rbp+var_60]; Buffer
0x18001c1f2  movdqa  [rbp+var_40], xmm1
0x18001c1f7  movdqa  [rbp+var_30], xmm0
0x18001c1fc  movups  [rbp+var_10], xmm0
0x18001c200  mov     [rbp+var_58], 0
0x18001c208  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x18001c210  mov     [rbp+var_18], 0
0x18001c214  call    cs:__imp_RtlLookupElementGenericTable
0x18001c21a  test    rax, rax
0x18001c21d  jz      short loc_18001C223
0x18001c21f  mov     rax, [rax+40h]
0x18001c223  cmp     [rbx+28h], rax
0x18001c227  jnz     short loc_18001C238
0x18001c229  mov     rdx, [rbx+88h]; unsigned __int64
0x18001c230  mov     rcx, rdi; this
0x18001c233  call    ?UpdateDesktopWindowReplacement@CWindowList@@AEAAJ_K@Z; CWindowList::UpdateDesktopWindowReplacement(unsigned __int64)
0x18001c238  cmp     qword ptr [rbx+18h], 0
0x18001c23d  jnz     short loc_18001C24A
0x18001c23f  mov     rdx, rbx; struct CWindowData *
0x18001c242  mov     rcx, rdi; this
0x18001c245  call    ?ImmediateDestroyWindow@CWindowList@@AEAAXPEAVCWindowData@@@Z; CWindowList::ImmediateDestroyWindow(CWindowData *)
0x18001c24a  lea     r11, [rsp+80h+var_s0]
0x18001c252  mov     rbx, [r11+30h]
0x18001c256  mov     rsi, [r11+38h]
0x18001c25a  mov     rsp, r11
0x18001c25d  pop     r14
0x18001c25f  pop     rdi
0x18001c260  pop     rbp
0x18001c261  retn
0x18001c262  cmp     dword ptr [rbx+80h], 1
0x18001c269  jz      short loc_18001C274
0x18001c26b  test    r14b, r14b
0x18001c26e  jnz     loc_18001C1A3
0x18001c274  mov     r8b, 1; bool
0x18001c277  mov     rdx, rbx; struct CWindowData *
0x18001c27a  mov     rcx, rdi; this
0x18001c27d  call    ?ShowHide@CWindowList@@QEAAJPEAVCWindowData@@_N@Z; CWindowList::ShowHide(CWindowData *,bool)
0x18001c282  jmp     loc_18001C1A3
0x18001c287  mov     ecx, 3
0x18001c28c  int     29h; Win8: RtlFailFast(ecx)
0x18001c28e  xor     edx, edx; pContextRecord
0x18001c290  xor     ecx, ecx; pExceptionRecord
0x18001c292  lea     r8d, [rdx+1]; dwFlags
0x18001c296  call    cs:__imp_RaiseFailFastException
0x18001c29c  jmp     loc_18001C145
```
