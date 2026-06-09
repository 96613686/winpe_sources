# CLockScreenHistory::_GetPreviewImage(ushort,uint,uint,bool,HBITMAP__ * *)

- ea: `0x1800c04ac`
- end: `0x1800c0674`
- name: `?_GetPreviewImage@CLockScreenHistory@@IEAAJGII_NPEAPEAUHBITMAP__@@@Z`
- size: `456`
- prototype: `int(CLockScreenHistory *__hidden this, unsigned __int16, unsigned int, unsigned int, bool, HBITMAP *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800b7c70`
- `0x1800c0e28`

## callees

- `0x1800b511c`
- `0x1800b7344`
- `0x1800b8ac4`
- `0x1800bfa50`
- `0x1800c04ac`
- `0x1800c067c`
- `0x1800c20e0`
- `0x1800ed010`

## import_xrefs

- `SHCORE!__imp_ScaleRelativePixelsForDevice` at `0x1800c0595`
- `SHCORE!__imp_ScaleRelativePixelsForDevice` at `0x1800c05b1`
- `SHCORE!__imp_ScaleRelativePixelsForDevice` at `0x1800c0595`
- `SHCORE!__imp_ScaleRelativePixelsForDevice` at `0x1800c05b1`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800c0512`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800c0512`
- `GDI32!DeleteObject` at `0x1800c062e`
- `GDI32!DeleteObject` at `0x1800c062e`

## pseudocode

```c
__int64 __fastcall CLockScreenHistory::_GetPreviewImage(
        CLockScreenHistory *this,
        unsigned __int16 a2,
        unsigned int a3,
        unsigned int a4,
        bool a5,
        HBITMAP *a6)
{
  HBITMAP *v6; // rdi
  HRESULT inited; // ebx
  CLockScreenHistory::CLockScreenHistoryEntry *v11; // rsi
  unsigned int v12; // edx
  unsigned int v13; // eax
  unsigned int v14; // r15d
  unsigned int v15; // r14d
  __int64 v16; // rbx
  unsigned int v17; // eax
  unsigned int v18; // edi
  char v20; // [rsp+20h] [rbp-40h]
  unsigned int v21; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+44h] [rbp-1Ch] BYREF
  HGDIOBJ ho; // [rsp+48h] [rbp-18h] BYREF
  void *ppv; // [rsp+50h] [rbp-10h] BYREF

  v6 = a6;
  if ( a6 )
    *a6 = 0;
  a6 = 0;
  inited = CLockScreenHistory::_CreateAndInitEntry(this, a2, (struct CLockScreenHistory::CLockScreenHistoryEntry **)&a6);
  if ( inited >= 0 )
  {
    v11 = (CLockScreenHistory::CLockScreenHistoryEntry *)a6;
    ppv = 0;
    inited = SHCreateItemFromParsingName((PCWSTR)a6 + 289, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( inited >= 0 )
    {
      v22 = 0;
      v21 = 0;
      inited = CLockScreenHistory::_GetPrimaryImageSize(this, &v22, &v21);
      if ( inited >= 0 )
      {
        if ( a3 && a4 && v6 )
        {
          *v6 = (HBITMAP)CLockScreenHistory::_s_CreatePreview((struct IShellItem *)ppv, a3, a4, a5, v22, v21);
        }
        else
        {
          ScaleRelativePixelsForDevice(1);
          v14 = v13;
          ScaleRelativePixelsForDevice(1);
          v15 = v21;
          v16 = 0;
          v18 = v17;
          LOWORD(a6) = 256;
          do
          {
            v20 = *((_BYTE *)&a6 + v16);
            LODWORD(ho) = 0;
            v21 = 0;
            if ( (int)GetPreviewWidthForMonitor(v18, v14, (float *)&ho, &v21, v20) >= 0 )
            {
              ho = 0;
              GetBitmapFromShellItem((struct IShellItem *)ppv, v21, v18, v22, v15, 0, (HBITMAP *)&ho);
              if ( ho )
                DeleteObject(ho);
            }
            ++v16;
          }
          while ( v16 != 2 );
          inited = 0;
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v11 )
      CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(v11, v12);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800c04ac  push    rbp
0x1800c04ae  push    rbx
0x1800c04af  push    rsi
0x1800c04b0  push    rdi
0x1800c04b1  push    r12
0x1800c04b3  push    r14
0x1800c04b5  push    r15
0x1800c04b7  mov     rbp, rsp
0x1800c04ba  sub     rsp, 60h
0x1800c04be  mov     rdi, [rbp+arg_28]
0x1800c04c2  mov     r15d, r9d
0x1800c04c5  mov     r12d, r8d
0x1800c04c8  mov     r14, rcx
0x1800c04cb  test    rdi, rdi
0x1800c04ce  jz      short loc_1800C04D7
0x1800c04d0  mov     qword ptr [rdi], 0
0x1800c04d7  lea     r8, [rbp+arg_28]; struct CLockScreenHistory::CLockScreenHistoryEntry **
0x1800c04db  mov     [rbp+arg_28], 0
0x1800c04e3  call    ?_CreateAndInitEntry@CLockScreenHistory@@IEAAJGPEAPEAVCLockScreenHistoryEntry@1@@Z; CLockScreenHistory::_CreateAndInitEntry(ushort,CLockScreenHistory::CLockScreenHistoryEntry * *)
0x1800c04e8  mov     ebx, eax
0x1800c04ea  test    eax, eax
0x1800c04ec  js      loc_1800C0662
0x1800c04f2  mov     rsi, [rbp+arg_28]
0x1800c04f6  lea     r9, [rbp+ppv]; ppv
0x1800c04fa  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800c0501  mov     [rbp+ppv], 0
0x1800c0509  xor     edx, edx; pbc
0x1800c050b  lea     rcx, [rsi+242h]; pszPath
0x1800c0512  call    cs:__imp_SHCreateItemFromParsingName
0x1800c0519  nop     dword ptr [rax+rax+00h]
0x1800c051e  mov     ebx, eax
0x1800c0520  test    eax, eax
0x1800c0522  js      loc_1800C0655
0x1800c0528  lea     r8, [rbp+var_20]; unsigned int *
0x1800c052c  mov     [rbp+var_1C], 0
0x1800c0533  lea     rdx, [rbp+var_1C]; unsigned int *
0x1800c0537  mov     [rbp+var_20], 0
0x1800c053e  mov     rcx, r14; this
0x1800c0541  call    ?_GetPrimaryImageSize@CLockScreenHistory@@IEAAJPEAI0@Z; CLockScreenHistory::_GetPrimaryImageSize(uint *,uint *)
0x1800c0546  mov     ebx, eax
0x1800c0548  test    eax, eax
0x1800c054a  js      loc_1800C0645
0x1800c0550  test    r12d, r12d
0x1800c0553  jz      short loc_1800C0588
0x1800c0555  test    r15d, r15d
0x1800c0558  jz      short loc_1800C0588
0x1800c055a  test    rdi, rdi
0x1800c055d  jz      short loc_1800C0588
0x1800c055f  mov     eax, [rbp+var_20]
0x1800c0562  mov     r8d, r15d; unsigned int
0x1800c0565  mov     r9b, [rbp+arg_20]; bool
0x1800c0569  mov     edx, r12d; unsigned int
0x1800c056c  mov     rcx, [rbp+ppv]; struct IShellItem *
0x1800c0570  mov     dword ptr [rsp+60h+var_38], eax; unsigned int
0x1800c0574  mov     eax, [rbp+var_1C]
0x1800c0577  mov     dword ptr [rsp+60h+var_40], eax; unsigned int
0x1800c057b  call    ?_s_CreatePreview@CLockScreenHistory@@KAPEAUHBITMAP__@@PEAUIShellItem@@II_NII@Z; CLockScreenHistory::_s_CreatePreview(IShellItem *,uint,uint,bool,uint,uint)
0x1800c0580  mov     [rdi], rax
0x1800c0583  jmp     loc_1800C0645
0x1800c0588  movss   xmm1, cs:__real@44160000
0x1800c0590  mov     ecx, 1
0x1800c0595  call    cs:__imp_ScaleRelativePixelsForDevice
0x1800c059c  nop     dword ptr [rax+rax+00h]
0x1800c05a1  movss   xmm1, cs:__real@43a88000
0x1800c05a9  mov     ecx, 1
0x1800c05ae  mov     r15d, eax
0x1800c05b1  call    cs:__imp_ScaleRelativePixelsForDevice
0x1800c05b8  nop     dword ptr [rax+rax+00h]
0x1800c05bd  mov     r14d, [rbp+var_20]
0x1800c05c1  xor     ebx, ebx
0x1800c05c3  mov     edi, eax
0x1800c05c5  mov     word ptr [rbp+arg_28], 100h
0x1800c05cb  mov     cl, byte ptr [rbp+rbx+arg_28]
0x1800c05cf  lea     r9, [rbp+var_20]; unsigned int *
0x1800c05d3  mov     [rsp+60h+var_40], cl; bool
0x1800c05d7  lea     r8, [rbp+ho]; float *
0x1800c05db  mov     ecx, edi; unsigned int
0x1800c05dd  mov     dword ptr [rbp+ho], 0
0x1800c05e4  mov     edx, r15d; unsigned int
0x1800c05e7  mov     [rbp+var_20], 0
0x1800c05ee  call    ?GetPreviewWidthForMonitor@@YAJIIPEAMPEAI_N@Z; GetPreviewWidthForMonitor(uint,uint,float *,uint *,bool)
0x1800c05f3  test    eax, eax
0x1800c05f5  js      short loc_1800C063A
0x1800c05f7  mov     r9d, [rbp+var_1C]; unsigned int
0x1800c05fb  lea     rax, [rbp+ho]
0x1800c05ff  mov     edx, [rbp+var_20]; unsigned int
0x1800c0602  mov     r8d, edi; unsigned int
0x1800c0605  mov     rcx, [rbp+ppv]; struct IShellItem *
0x1800c0609  mov     [rsp+60h+var_30], rax; HBITMAP *
0x1800c060e  mov     [rsp+60h+var_38], 0; bool
0x1800c0613  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x1800c0618  mov     [rbp+ho], 0
0x1800c0620  call    ?GetBitmapFromShellItem@@YAXPEAUIShellItem@@IIII_NPEAPEAUHBITMAP__@@@Z; GetBitmapFromShellItem(IShellItem *,uint,uint,uint,uint,bool,HBITMAP__ * *)
0x1800c0625  mov     rcx, [rbp+ho]; ho
0x1800c0629  test    rcx, rcx
0x1800c062c  jz      short loc_1800C063A
0x1800c062e  call    cs:__imp_DeleteObject
0x1800c0635  nop     dword ptr [rax+rax+00h]
0x1800c063a  inc     rbx
0x1800c063d  cmp     rbx, 2
0x1800c0641  jnz     short loc_1800C05CB
0x1800c0643  xor     ebx, ebx
0x1800c0645  mov     rcx, [rbp+ppv]
0x1800c0649  mov     rax, [rcx]
0x1800c064c  mov     rax, [rax+10h]
0x1800c0650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0655  test    rsi, rsi
0x1800c0658  jz      short loc_1800C0662
0x1800c065a  mov     rcx, rsi; this
0x1800c065d  call    ??_GCLockScreenHistoryEntry@CLockScreenHistory@@QEAAPEAXI@Z; CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(uint)
0x1800c0662  mov     eax, ebx
0x1800c0664  add     rsp, 60h
0x1800c0668  pop     r15
0x1800c066a  pop     r14
0x1800c066c  pop     r12
0x1800c066e  pop     rdi
0x1800c066f  pop     rsi
0x1800c0670  pop     rbx
0x1800c0671  pop     rbp
0x1800c0672  retn
```
