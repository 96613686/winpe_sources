# File::WriteFileHeader(void *,FileHeader *,bool,bool,FileModeFlags)

- ea: `0x180033078`
- end: `0x180033164`
- name: `?WriteFileHeader@File@@CAKPEAXPEAUFileHeader@@_N2W4FileModeFlags@@@Z`
- size: `236`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800315f8`
- `0x180031cf4`
- `0x1800322f0`
- `0x1800325e8`
- `0x18003459c`

## callees

- `0x180023548`
- `0x180033078`
- `0x180033b4c`
- `0x180034fd8`
- `0x180034ffc`
- `0x180035290`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180033140`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180033140`

## pseudocode

```c
__int64 __fastcall File::WriteFileHeader(void *a1, __int64 a2, __int64 a3, char a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // r9d
  int v10; // r10d
  unsigned int v11; // eax
  int v12; // r10d
  unsigned int v13; // ebx
  _BYTE v15[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+28h] [rbp-30h]
  __int64 v17; // [rsp+30h] [rbp-28h]
  unsigned int v18; // [rsp+40h] [rbp-18h]
  char v19; // [rsp+49h] [rbp-Fh]

  v16 = -1;
  v17 = a2;
  v18 = 128;
  v19 = 0;
  FileView::SetPointers((FileView *)v15);
  v10 = *(_DWORD *)(a2 + 120);
  v16 = 0;
  v11 = v10 & 0xFFFFFFFE;
  v12 = v10 | 1;
  if ( !(_BYTE)v8 )
    v12 = v11;
  *(_DWORD *)(a2 + 120) = v12;
  *(_DWORD *)(a2 + 124) = CalcGeneralHeaderCRC((PUCHAR)a2, v7, v8, v9);
  v13 = FileView::ActualWrite((FileView *)v15, a1, 0, v18);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v13);
    }
  }
  else
  {
    if ( a4 )
      FlushFileBuffers(a1);
    v13 = 0;
  }
  FileView::~FileView((FileView *)v15);
  return v13;
}

```

## disassembly

```asm
0x180033078  mov     rax, rsp
0x18003307b  mov     [rax+8], rbx
0x18003307f  mov     [rax+10h], rsi
0x180033083  push    rdi
0x180033084  sub     rsp, 50h
0x180033088  mov     sil, r9b
0x18003308b  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFFh
0x180033093  mov     r9d, 80h
0x180033099  mov     [rax-28h], rdx
0x18003309d  mov     rdi, rcx
0x1800330a0  mov     [rax-18h], r9d
0x1800330a4  lea     rcx, [rax-38h]; this
0x1800330a8  mov     byte ptr [rax-0Fh], 0
0x1800330ac  mov     rbx, rdx
0x1800330af  call    ?SetPointers@FileView@@QEAAXXZ; FileView::SetPointers(void)
0x1800330b4  mov     r10d, [rbx+78h]
0x1800330b8  mov     rcx, rbx; Buffer
0x1800330bb  mov     eax, r10d
0x1800330be  mov     [rsp+58h+var_30], 0
0x1800330c7  and     eax, 0FFFFFFFEh
0x1800330ca  or      r10d, 1
0x1800330ce  test    r8b, r8b
0x1800330d1  cmovz   r10d, eax
0x1800330d5  mov     [rbx+78h], r10d
0x1800330d9  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x1800330de  mov     [rbx+7Ch], eax
0x1800330e1  lea     rcx, [rsp+58h+var_38]; this
0x1800330e6  mov     r9d, [rsp+58h+var_18]; unsigned int
0x1800330eb  xor     r8d, r8d; unsigned int
0x1800330ee  mov     rdx, rdi; void *
0x1800330f1  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x1800330f6  mov     ebx, eax
0x1800330f8  test    eax, eax
0x1800330fa  jz      short loc_180033138
0x1800330fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180033103  lea     rax, WPP_GLOBAL_Control
0x18003310a  cmp     rcx, rax
0x18003310d  jz      short loc_180033148
0x18003310f  test    dword ptr [rcx+1Ch], 8000h
0x180033116  jz      short loc_180033148
0x180033118  cmp     byte ptr [rcx+19h], 2
0x18003311c  jb      short loc_180033148
0x18003311e  mov     rcx, [rcx+10h]
0x180033122  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180033129  mov     edx, 0Ah
0x18003312e  mov     r9d, ebx
0x180033131  call    WPP_SF_D
0x180033136  jmp     short loc_180033148
0x180033138  test    sil, sil
0x18003313b  jz      short loc_180033146
0x18003313d  mov     rcx, rdi; hFile
0x180033140  call    cs:__imp_FlushFileBuffers
0x180033146  xor     ebx, ebx
0x180033148  lea     rcx, [rsp+58h+var_38]; this
0x18003314d  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180033152  mov     rsi, [rsp+58h+arg_8]
0x180033157  mov     eax, ebx
0x180033159  mov     rbx, [rsp+58h+arg_0]
0x18003315e  add     rsp, 50h
0x180033162  pop     rdi
0x180033163  retn
```
