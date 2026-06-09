# DuiView::Initialize(ushort const *,_CREDSDLG_PROPERTIES *)

- ea: `0x180017fcc`
- end: `0x18001818e`
- name: `?Initialize@DuiView@@AEAAJPEBGPEAU_CREDSDLG_PROPERTIES@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(DuiView *__hidden this, const unsigned __int16 *, struct _CREDSDLG_PROPERTIES *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180017ca0`

## callees

- `0x1800011d0`
- `0x180001e26`
- `0x180017ab8`
- `0x180017fcc`
- `0x18001d010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800180db`
- `KERNEL32!HeapAlloc` at `0x1800180db`
- `KERNEL32!GetProcessHeap` at `0x1800180ca`
- `KERNEL32!GetProcessHeap` at `0x1800180ca`
- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHIPEAPEAV12@@Z` at `0x180018073`
- `DUI70!?Create@NativeHWNDHost@DirectUI@@SAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHIPEAPEAV12@@Z` at `0x180018073`

## string_xrefs

- `0x1800180a1`: `<duixml>  <element resid="main" layout="borderlayout()">    <element layout="rowlayout(1)" layoutpos="top">      <element content="Display error: no display input specified" />    </element>    <element layout="rowlayout(1)" layoutpos="top">      <button active="keyboard|mouse" layout="borderlayout()">        <element id="atom(inner)" layoutpos="left" />        <element content="OK" />      </button>    </element>  </element></duixml>`

## pseudocode

```c
__int64 __fastcall DuiView::Initialize(DuiView *this, const unsigned __int16 *a2, struct _CREDSDLG_PROPERTIES *a3)
{
  __int64 v6; // rax
  unsigned int v7; // edx
  const unsigned __int16 *v8; // rcx
  struct DirectUI::Element *v9; // rdx
  unsigned int *v10; // r8
  int v11; // r14d
  _QWORD *v12; // rsi
  __int64 v13; // r13
  __int64 v14; // rbp
  __int64 v15; // rbx
  HANDLE ProcessHeap; // rax
  void *v17; // rax
  _QWORD *v18; // rdx
  _QWORD *v19; // rax

  *(_OWORD *)((char *)this + 24) = *(_OWORD *)a3;
  v6 = *((_QWORD *)this + 4);
  if ( !v6 || *(_DWORD *)v6 != 1 || (v7 = 0x80000000, *(_DWORD *)(v6 + 20) != 1) )
    v7 = 12583040;
  if ( !v6 || *(_DWORD *)(v6 + 20) == 1 )
  {
    v8 = 0;
  }
  else if ( !*(_DWORD *)(v6 + 4) || (v8 = *(const unsigned __int16 **)(v6 + 24)) == 0 )
  {
    v8 = L"Enter your credentials";
  }
  v11 = DirectUI::NativeHWNDHost::Create(
          v8,
          *((HWND *)this + 6),
          0,
          0x80000000,
          0x80000000,
          0x80000000,
          0x80000000,
          0,
          v7,
          *(_DWORD *)a3 != 0 ? 28 : 24,
          (struct DirectUI::NativeHWNDHost **)this);
  if ( v11 >= 0 )
  {
    v12 = (_QWORD *)((char *)this + 8);
    v11 = TopViewer::Create(*(struct DirectUI::NativeHWNDHost **)this, v9, v10, (struct DirectUI::Element **)this + 1);
    if ( v11 >= 0 )
    {
      v13 = *v12;
      if ( !a2 )
        a2 = L"<duixml>  <element resid=\"main\" layout=\"borderlayout()\">    <element layout=\"rowlayout(1)\" layoutpos="
              "\"top\">      <element content=\"Display error: no display input specified\" />    </element>    <element "
              "layout=\"rowlayout(1)\" layoutpos=\"top\">      <button active=\"keyboard|mouse\" layout=\"borderlayout()\""
              ">        <element id=\"atom(inner)\" layoutpos=\"left\" />        <element content=\"OK\" />      </button"
              ">    </element>  </element></duixml>";
      v14 = -1;
      v15 = -1;
      do
        ++v15;
      while ( a2[v15] );
      ProcessHeap = GetProcessHeap();
      v17 = HeapAlloc(ProcessHeap, 8u, 2 * v15 + 2);
      *(_QWORD *)(v13 + 816) = v17;
      if ( v17 )
      {
        do
          ++v14;
        while ( a2[v14] );
        memcpy_0(v17, a2, 2 * v14 + 2);
      }
      *(_QWORD *)(*v12 + 824LL) = *((_QWORD *)this + 5);
      v18 = (_QWORD *)*((_QWORD *)this + 2);
      if ( !v18 )
      {
        if ( *(_DWORD *)(*((_QWORD *)a3 + 1) + 20LL) == 1 )
        {
          v19 = operator new(0x10u);
          v18 = v19;
          if ( v19 )
          {
            *v19 = *v12;
            v19[1] = a3;
          }
          else
          {
            v18 = 0;
          }
          *((_QWORD *)this + 2) = v18;
        }
        else
        {
          v18 = 0;
        }
      }
      *(_QWORD *)(*v12 + 272LL) = v18;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 168LL))(*v12);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180017fcc  push    rbx
0x180017fce  push    rbp
0x180017fcf  push    rsi
0x180017fd0  push    rdi
0x180017fd1  push    r12
0x180017fd3  push    r13
0x180017fd5  push    r14
0x180017fd7  push    r15
0x180017fd9  sub     rsp, 68h
0x180017fdd  movups  xmm0, xmmword ptr [r8]
0x180017fe1  mov     r12, r8
0x180017fe4  mov     r15, rdx
0x180017fe7  mov     rdi, rcx
0x180017fea  movdqu  xmmword ptr [rcx+18h], xmm0
0x180017fef  mov     eax, [r8]
0x180017ff2  mov     r8d, 80000000h
0x180017ff8  neg     eax
0x180017ffa  mov     rax, [rcx+20h]
0x180017ffe  sbb     r9d, r9d
0x180018001  xor     ebx, ebx
0x180018003  and     r9d, 4
0x180018007  add     r9d, 18h
0x18001800b  test    rax, rax
0x18001800e  jz      short loc_18001801E
0x180018010  cmp     dword ptr [rax], 1
0x180018013  jnz     short loc_18001801E
0x180018015  cmp     dword ptr [rax+14h], 1
0x180018019  mov     edx, r8d
0x18001801c  jz      short loc_180018023
0x18001801e  mov     edx, 0C00080h
0x180018023  test    rax, rax
0x180018026  jz      short loc_180018045
0x180018028  cmp     dword ptr [rax+14h], 1
0x18001802c  jz      short loc_180018045
0x18001802e  cmp     [rax+4], ebx
0x180018031  jz      short loc_18001803C
0x180018033  mov     rcx, [rax+18h]
0x180018037  test    rcx, rcx
0x18001803a  jnz     short loc_180018048
0x18001803c  lea     rcx, aEnterYourCrede; "Enter your credentials"
0x180018043  jmp     short loc_180018048
0x180018045  mov     rcx, rbx
0x180018048  mov     [rsp+0A8h+var_58], rdi
0x18001804d  mov     [rsp+0A8h+var_60], r9d
0x180018052  mov     r9d, r8d
0x180018055  mov     [rsp+0A8h+var_68], edx
0x180018059  mov     rdx, [rdi+30h]
0x18001805d  mov     [rsp+0A8h+var_70], ebx
0x180018061  mov     [rsp+0A8h+var_78], r8d
0x180018066  mov     [rsp+0A8h+var_80], r8d
0x18001806b  mov     [rsp+0A8h+var_88], r8d
0x180018070  xor     r8d, r8d
0x180018073  call    cs:__imp_?Create@NativeHWNDHost@DirectUI@@SAJPEBGPEAUHWND__@@PEAUHICON__@@HHHHHHIPEAPEAV12@@Z; DirectUI::NativeHWNDHost::Create(ushort const *,HWND__ *,HICON__ *,int,int,int,int,int,int,uint,DirectUI::NativeHWNDHost * *)
0x180018079  mov     r14d, eax
0x18001807c  test    eax, eax
0x18001807e  js      loc_18001817A
0x180018084  mov     rcx, [rdi]; struct DirectUI::NativeHWNDHost *
0x180018087  lea     rsi, [rdi+8]
0x18001808b  mov     r9, rsi; struct DirectUI::Element **
0x18001808e  call    ?Create@TopViewer@@SAJPEAVNativeHWNDHost@DirectUI@@PEAVElement@3@PEAKPEAPEAV43@@Z; TopViewer::Create(DirectUI::NativeHWNDHost *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180018093  mov     r14d, eax
0x180018096  test    eax, eax
0x180018098  js      loc_18001817A
0x18001809e  mov     r13, [rsi]
0x1800180a1  lea     rax, aDuixmlElementR_1; "<duixml>  <element resid=\"main\" layou"...
0x1800180a8  test    r15, r15
0x1800180ab  cmovz   r15, rax
0x1800180af  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800180b3  mov     rbx, rbp
0x1800180b6  xor     eax, eax
0x1800180b8  inc     rbx
0x1800180bb  cmp     [r15+rbx*2], ax
0x1800180c0  jnz     short loc_1800180B8
0x1800180c2  lea     rbx, ds:2[rbx*2]
0x1800180ca  call    cs:__imp_GetProcessHeap
0x1800180d0  mov     r8, rbx; dwBytes
0x1800180d3  mov     edx, 8; dwFlags
0x1800180d8  mov     rcx, rax; hHeap
0x1800180db  call    cs:__imp_HeapAlloc
0x1800180e1  xor     ebx, ebx
0x1800180e3  mov     [r13+330h], rax
0x1800180ea  test    rax, rax
0x1800180ed  jz      short loc_18001810C
0x1800180ef  inc     rbp
0x1800180f2  cmp     [r15+rbp*2], bx
0x1800180f7  jnz     short loc_1800180EF
0x1800180f9  lea     r8, ds:2[rbp*2]; Size
0x180018101  mov     rdx, r15; Src
0x180018104  mov     rcx, rax; void *
0x180018107  call    memcpy_0
0x18001810c  mov     rcx, [rsi]
0x18001810f  mov     rax, [rdi+28h]
0x180018113  mov     [rcx+338h], rax
0x18001811a  mov     rdx, [rdi+10h]
0x18001811e  test    rdx, rdx
0x180018121  jnz     short loc_18001815E
0x180018123  mov     rax, [r12+8]
0x180018128  cmp     dword ptr [rax+14h], 1
0x18001812c  jnz     short loc_18001815B
0x18001812e  lea     ecx, [rdx+10h]; Size
0x180018131  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018136  mov     [rsp+0A8h+arg_0], rax
0x18001813e  mov     rdx, rax
0x180018141  test    rax, rax
0x180018144  jz      short loc_180018152
0x180018146  mov     rcx, [rsi]
0x180018149  mov     [rax], rcx
0x18001814c  mov     [rax+8], r12
0x180018150  jmp     short loc_180018155
0x180018152  mov     rdx, rbx
0x180018155  mov     [rdi+10h], rdx
0x180018159  jmp     short loc_18001815E
0x18001815b  mov     rdx, rbx
0x18001815e  mov     rax, [rsi]
0x180018161  mov     [rax+110h], rdx
0x180018168  mov     rcx, [rsi]
0x18001816b  mov     rax, [rcx]
0x18001816e  mov     rax, [rax+0A8h]
0x180018175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001817a  mov     eax, r14d
0x18001817d  add     rsp, 68h
0x180018181  pop     r15
0x180018183  pop     r14
0x180018185  pop     r13
0x180018187  pop     r12
0x180018189  pop     rdi
0x18001818a  pop     rsi
0x18001818b  pop     rbp
0x18001818c  pop     rbx
0x18001818d  retn
```
