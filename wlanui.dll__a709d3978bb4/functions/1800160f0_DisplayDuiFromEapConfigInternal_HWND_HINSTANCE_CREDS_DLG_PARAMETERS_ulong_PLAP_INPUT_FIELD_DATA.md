# DisplayDuiFromEapConfigInternal(HWND__ *,HINSTANCE__ *,_CREDS_DLG_PARAMETERS *,ulong,_PLAP_INPUT_FIELD_DATA *)

- ea: `0x1800160f0`
- end: `0x1800161f6`
- name: `?DisplayDuiFromEapConfigInternal@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEAU_CREDS_DLG_PARAMETERS@@KPEAU_PLAP_INPUT_FIELD_DATA@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, struct _CREDS_DLG_PARAMETERS *, unsigned int, struct _PLAP_INPUT_FIELD_DATA *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180016200`
- `0x180016b60`

## callees

- `0x1800011d0`
- `0x1800160f0`
- `0x180016d4c`
- `0x180017ca0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800161a0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800161a0`
- `ole32!OleInitialize` at `0x18001610b`
- `ole32!OleInitialize` at `0x18001610b`
- `ole32!OleUninitialize` at `0x1800161b9`
- `ole32!OleUninitialize` at `0x1800161b9`
- `DUI70!UnInitThread` at `0x1800161a6`
- `DUI70!UnInitThread` at `0x1800161a6`
- `DUI70!UnInitProcessPriv` at `0x1800161b3`
- `DUI70!UnInitProcessPriv` at `0x1800161b3`
- `DUI70!InitThread` at `0x18001613d`
- `DUI70!InitThread` at `0x18001613d`
- `DUI70!InitProcessPriv` at `0x180016130`
- `DUI70!InitProcessPriv` at `0x180016130`

## pseudocode

```c
__int64 __fastcall DisplayDuiFromEapConfigInternal(
        HWND a1,
        HINSTANCE a2,
        struct _CREDS_DLG_PARAMETERS *a3,
        unsigned int a4,
        struct _PLAP_INPUT_FIELD_DATA *a5)
{
  __int64 v9; // r8
  int v10; // ebx
  DuiView *v11; // rax
  DuiView *v12; // rdi

  if ( OleInitialize(0) < 0 )
    return 0;
  v10 = 0;
  LOBYTE(v9) = 1;
  if ( (int)InitProcessPriv(14, &_ImageBase, v9) >= 0 )
  {
    if ( (int)InitThread(2) >= 0 )
    {
      v11 = (DuiView *)operator new(0x40u);
      v12 = v11;
      if ( v11 )
      {
        *((_QWORD *)v11 + 2) = 0;
        *((_QWORD *)v11 + 5) = 0;
        *((_QWORD *)v11 + 6) = 0;
        *((_QWORD *)v11 + 7) = 0;
        v10 = DuiView::DisplayDuiFromEapConfig(v11, a1, a2, a3, a4, a5);
        DuiView::~DuiView(v12);
        operator delete(v12);
      }
      UnInitThread();
    }
    UnInitProcessPriv(&_ImageBase);
  }
  OleUninitialize();
  if ( v10 == 1223 )
  {
    *((_DWORD *)a3 + 4) = 1;
    return 0;
  }
  if ( v10 >= 0 )
    return 0;
  if ( (v10 & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)v10;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800160f0  push    rbx
0x1800160f2  push    rbp
0x1800160f3  push    rsi
0x1800160f4  push    rdi
0x1800160f5  push    r14
0x1800160f7  push    r15
0x1800160f9  sub     rsp, 48h
0x1800160fd  mov     r15, rcx
0x180016100  mov     ebp, r9d
0x180016103  xor     ecx, ecx; pvReserved
0x180016105  mov     rsi, r8
0x180016108  mov     r14, rdx
0x18001610b  call    cs:__imp_OleInitialize
0x180016111  test    eax, eax
0x180016113  js      loc_1800161CE
0x180016119  mov     r9b, 1
0x18001611c  mov     byte ptr [rsp+78h+var_58], 1
0x180016121  xor     ebx, ebx
0x180016123  lea     rdx, __ImageBase
0x18001612a  mov     r8b, r9b
0x18001612d  lea     ecx, [rbx+0Eh]
0x180016130  call    cs:__imp_InitProcessPriv
0x180016136  test    eax, eax
0x180016138  js      short loc_1800161B9
0x18001613a  lea     ecx, [rbx+2]
0x18001613d  call    cs:__imp_InitThread
0x180016143  test    eax, eax
0x180016145  js      short loc_1800161AC
0x180016147  lea     ecx, [rbx+40h]; Size
0x18001614a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001614f  mov     [rsp+78h+var_48], rax
0x180016154  mov     rdi, rax
0x180016157  test    rax, rax
0x18001615a  jz      short loc_1800161A6
0x18001615c  mov     [rax+10h], rbx
0x180016160  mov     [rax+28h], rbx
0x180016164  mov     [rax+30h], rbx
0x180016168  mov     [rax+38h], rbx
0x18001616c  test    rax, rax
0x18001616f  jz      short loc_1800161A6
0x180016171  mov     rax, [rsp+78h+arg_20]
0x180016179  mov     r9, rsi; struct _CREDS_DLG_PARAMETERS *
0x18001617c  mov     [rsp+78h+var_50], rax; struct _PLAP_INPUT_FIELD_DATA *
0x180016181  mov     r8, r14; HINSTANCE
0x180016184  mov     rdx, r15; HWND
0x180016187  mov     [rsp+78h+var_58], ebp; unsigned int
0x18001618b  mov     rcx, rdi; this
0x18001618e  call    ?DisplayDuiFromEapConfig@DuiView@@QEAAJPEAUHWND__@@PEAUHINSTANCE__@@PEAU_CREDS_DLG_PARAMETERS@@KPEAU_PLAP_INPUT_FIELD_DATA@@@Z; DuiView::DisplayDuiFromEapConfig(HWND__ *,HINSTANCE__ *,_CREDS_DLG_PARAMETERS *,ulong,_PLAP_INPUT_FIELD_DATA *)
0x180016193  mov     rcx, rdi; this
0x180016196  mov     ebx, eax
0x180016198  call    ??1DuiView@@QEAA@XZ; DuiView::~DuiView(void)
0x18001619d  mov     rcx, rdi
0x1800161a0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800161a6  call    cs:__imp_UnInitThread
0x1800161ac  lea     rcx, __ImageBase
0x1800161b3  call    cs:__imp_UnInitProcessPriv
0x1800161b9  call    cs:__imp_OleUninitialize
0x1800161bf  cmp     ebx, 4C7h
0x1800161c5  jnz     short loc_1800161DF
0x1800161c7  mov     dword ptr [rsi+10h], 1
0x1800161ce  xor     ebx, ebx
0x1800161d0  mov     eax, ebx
0x1800161d2  add     rsp, 48h
0x1800161d6  pop     r15
0x1800161d8  pop     r14
0x1800161da  pop     rdi
0x1800161db  pop     rsi
0x1800161dc  pop     rbp
0x1800161dd  pop     rbx
0x1800161de  retn
0x1800161df  test    ebx, ebx
0x1800161e1  jns     short loc_1800161CE
0x1800161e3  mov     eax, ebx
0x1800161e5  and     eax, 1FFF0000h
0x1800161ea  cmp     eax, 70000h
0x1800161ef  jnz     short loc_1800161D0
0x1800161f1  movzx   ebx, bx
0x1800161f4  jmp     short loc_1800161D0
```
