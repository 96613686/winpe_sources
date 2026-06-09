# CWMFileSinkV1::InternalOpen(ushort const *)

- ea: `0x180009820`
- end: `0x180009b31`
- name: `?InternalOpen@CWMFileSinkV1@@MEAAJPEBG@Z`
- size: `785`
- prototype: `int(CWMFileSinkV1 *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800039f0`

## callees

- `0x180001194`
- `0x1800011a0`
- `0x1800011ec`
- `0x180005060`
- `0x18000774c`
- `0x180007f74`
- `0x180009820`
- `0x18000cd9c`
- `0x18002b010`

## import_xrefs

- `KERNEL32!GetFileType` at `0x180009982`
- `KERNEL32!GetFileType` at `0x180009982`
- `KERNEL32!CloseHandle` at `0x180009999`
- `KERNEL32!CloseHandle` at `0x180009999`
- `KERNEL32!CreateFileW` at `0x180009966`
- `KERNEL32!CreateFileW` at `0x180009966`
- `KERNEL32!LeaveCriticalSection` at `0x180009b10`
- `KERNEL32!LeaveCriticalSection` at `0x180009b10`
- `KERNEL32!EnterCriticalSection` at `0x180009843`
- `KERNEL32!EnterCriticalSection` at `0x180009843`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::InternalOpen(CWMFileSinkV1 *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  int v5; // esi
  __int64 v6; // rbp
  _QWORD *v7; // rax
  int v8; // r8d
  unsigned int v9; // edx
  CUnbufferedWriter *v10; // rcx
  HANDLE FileW; // rax
  void *v12; // rcx
  unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // r15
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  unsigned __int16 i; // bp
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v22; // [rsp+70h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_36;
  }
  v6 = -1;
  v5 = 0;
  if ( !*((_DWORD *)this + 9) )
    goto LABEL_13;
  if ( *((_QWORD *)this + 1158) )
  {
    v5 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *))(*(_QWORD *)this + 112LL))(this);
    if ( v5 < 0 )
      goto LABEL_36;
  }
  v7 = operator new(0x58u);
  if ( !v7 )
    goto LABEL_10;
  v7[2] = 0;
  v7[3] = -1;
  v7[4] = -1;
  v7[5] = 0;
  v7[6] = 0;
  v7[7] = 0;
  *((_DWORD *)v7 + 16) = 0;
  v7[9] = -1;
  v7[10] = 0;
  *v7 = 0;
  v7[1] = 0;
  v8 = *((_DWORD *)this + 10);
  *((_QWORD *)this + 1158) = v7;
  v5 = CUnbufferedWriter::OpenFile((unsigned __int16 **)v7, a2, v8);
  if ( v5 < 0 )
  {
    v10 = (CUnbufferedWriter *)*((_QWORD *)this + 1158);
    if ( v10 )
    {
      CUnbufferedWriter::`scalar deleting destructor'(v10, v9);
LABEL_10:
      *((_QWORD *)this + 1158) = 0;
    }
  }
  if ( !*((_QWORD *)this + 1158) )
    *((_DWORD *)this + 9) = 0;
LABEL_13:
  if ( !*((_DWORD *)this + 9) )
  {
    if ( *((_QWORD *)this + 24) != -1 )
    {
      v5 = (*(__int64 (__fastcall **)(CWMFileSinkV1 *))(*(_QWORD *)this + 112LL))(this);
      if ( v5 < 0 )
        goto LABEL_36;
    }
    FileW = CreateFileW(a2, 0x40000000u, *((_DWORD *)this + 53), 0, *((_DWORD *)this + 54), *((_DWORD *)this + 52), 0);
    *((_QWORD *)this + 24) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v5 = -1072889827;
    }
    else if ( GetFileType(FileW) != 1 )
    {
      v12 = (void *)*((_QWORD *)this + 24);
      if ( v12 != (void *)-1LL )
      {
        CloseHandle(v12);
        *((_QWORD *)this + 24) = -1;
      }
      v5 = -1072889828;
    }
  }
  v13 = (unsigned __int16 *)*((_QWORD *)this + 25);
  if ( a2 != v13 )
  {
    if ( v13 )
    {
      operator delete(v13, 2u);
      *((_QWORD *)this + 25) = 0;
    }
    v22 = 0;
    StringCchLengthW(a2, 0x104u, &v22);
    v14 = v22 + 1;
    v15 = (unsigned __int16 *)operator new[](saturated_mul(v22 + 1, 2u));
    *((_QWORD *)this + 25) = v15;
    if ( !v15 )
    {
      v5 = -2147024882;
      goto LABEL_36;
    }
    StringCchCopyW(v15, v14, a2);
  }
  *((_DWORD *)this + 2314) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 920) = 0;
  *((_QWORD *)this + 42) = 0;
  if ( *((_DWORD *)this + 7) )
  {
    v6 = *((_QWORD *)this + 34);
    *((_QWORD *)this + 38) = v6;
    *((_QWORD *)this + 39) = v6;
  }
  *((_QWORD *)this + 37) = v6;
  v16 = 0;
  v17 = 0;
  do
  {
    ++v16;
    *(_QWORD *)((char *)this + v17 + 344) = 0;
    *(_QWORD *)((char *)this + v17 + 352) = 0;
    *(_QWORD *)((char *)this + v17 + 360) = 0;
    *(_DWORD *)((char *)this + v17 + 368) = 0;
    *(_WORD *)((char *)this + v17 + 372) = 0;
    v17 += 48;
  }
  while ( v16 != 64 );
  for ( i = 0; i < *((_WORD *)this + 4196); ++i )
  {
    v19 = *((_QWORD *)this + i + 985);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
  }
  v20 = *((_QWORD *)this + 1052);
  *((_QWORD *)this + 41) = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 56LL))(v20);
LABEL_36:
  LeaveCriticalSection(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009820  mov     [rsp+arg_8], rbx
0x180009825  mov     [rsp+arg_10], rbp
0x18000982a  push    rsi
0x18000982b  push    rdi
0x18000982c  push    r12
0x18000982e  push    r14
0x180009830  push    r15
0x180009832  sub     rsp, 40h
0x180009836  lea     rbx, [rcx+30h]
0x18000983a  mov     rdi, rcx
0x18000983d  mov     rcx, rbx; lpCriticalSection
0x180009840  mov     r14, rdx
0x180009843  call    cs:__imp_EnterCriticalSection
0x180009849  xor     r12d, r12d
0x18000984c  test    r14, r14
0x18000984f  jnz     short loc_18000985B
0x180009851  mov     esi, 80070057h
0x180009856  jmp     loc_180009B0D
0x18000985b  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000985f  mov     esi, r12d
0x180009862  cmp     [rdi+24h], r12d
0x180009866  jz      loc_180009909
0x18000986c  cmp     [rdi+2430h], r12
0x180009873  jz      short loc_18000988E
0x180009875  mov     rax, [rdi]
0x180009878  mov     rcx, rdi
0x18000987b  mov     rax, [rax+70h]
0x18000987f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009884  mov     esi, eax
0x180009886  test    eax, eax
0x180009888  js      loc_180009B0D
0x18000988e  mov     ecx, 58h ; 'X'; Size
0x180009893  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009898  test    rax, rax
0x18000989b  jz      short loc_1800098F5
0x18000989d  mov     [rax+10h], r12
0x1800098a1  mov     rdx, r14; unsigned __int16 *
0x1800098a4  mov     [rax+18h], rbp
0x1800098a8  mov     rcx, rax; this
0x1800098ab  mov     [rax+20h], rbp
0x1800098af  mov     [rax+28h], r12
0x1800098b3  mov     [rax+30h], r12
0x1800098b7  mov     [rax+38h], r12
0x1800098bb  mov     [rax+40h], r12d
0x1800098bf  mov     [rax+48h], rbp
0x1800098c3  mov     [rax+50h], r12
0x1800098c7  mov     [rax], r12
0x1800098ca  mov     [rax+8], r12
0x1800098ce  mov     r8d, [rdi+28h]; int
0x1800098d2  mov     [rdi+2430h], rax
0x1800098d9  call    ?OpenFile@CUnbufferedWriter@@QEAAJPEBGH@Z; CUnbufferedWriter::OpenFile(ushort const *,int)
0x1800098de  mov     esi, eax
0x1800098e0  test    eax, eax
0x1800098e2  jns     short loc_1800098FC
0x1800098e4  mov     rcx, [rdi+2430h]; this
0x1800098eb  test    rcx, rcx
0x1800098ee  jz      short loc_1800098FC
0x1800098f0  call    ??_GCUnbufferedWriter@@QEAAPEAXI@Z; CUnbufferedWriter::`scalar deleting destructor'(uint)
0x1800098f5  mov     [rdi+2430h], r12
0x1800098fc  cmp     [rdi+2430h], r12
0x180009903  jnz     short loc_180009909
0x180009905  mov     [rdi+24h], r12d
0x180009909  mov     r15d, 1
0x18000990f  cmp     [rdi+24h], r12d
0x180009913  jnz     loc_1800099AB
0x180009919  cmp     [rdi+0C0h], rbp
0x180009920  jz      short loc_18000993B
0x180009922  mov     rax, [rdi]
0x180009925  mov     rcx, rdi
0x180009928  mov     rax, [rax+70h]
0x18000992c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009931  mov     esi, eax
0x180009933  test    eax, eax
0x180009935  js      loc_180009B0D
0x18000993b  mov     eax, [rdi+0D0h]
0x180009941  xor     r9d, r9d; lpSecurityAttributes
0x180009944  mov     r8d, [rdi+0D4h]; dwShareMode
0x18000994b  mov     edx, 40000000h; dwDesiredAccess
0x180009950  mov     [rsp+68h+hTemplateFile], r12; hTemplateFile
0x180009955  mov     rcx, r14; lpFileName
0x180009958  mov     [rsp+68h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000995c  mov     eax, [rdi+0D8h]
0x180009962  mov     [rsp+68h+dwCreationDisposition], eax; dwCreationDisposition
0x180009966  call    cs:__imp_CreateFileW
0x18000996c  mov     [rdi+0C0h], rax
0x180009973  cmp     rax, rbp
0x180009976  jnz     short loc_18000997F
0x180009978  mov     esi, 0C00D001Dh
0x18000997d  jmp     short loc_1800099AB
0x18000997f  mov     rcx, rax; hFile
0x180009982  call    cs:__imp_GetFileType
0x180009988  cmp     eax, r15d
0x18000998b  jz      short loc_1800099AB
0x18000998d  mov     rcx, [rdi+0C0h]; hObject
0x180009994  cmp     rcx, rbp
0x180009997  jz      short loc_1800099A6
0x180009999  call    cs:__imp_CloseHandle
0x18000999f  mov     [rdi+0C0h], rbp
0x1800099a6  mov     esi, 0C00D001Ch
0x1800099ab  mov     rcx, [rdi+0C8h]; void *
0x1800099b2  cmp     r14, rcx
0x1800099b5  jz      short loc_180009A2A
0x1800099b7  test    rcx, rcx
0x1800099ba  jz      short loc_1800099CD
0x1800099bc  mov     edx, 2; unsigned __int64
0x1800099c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800099c6  mov     [rdi+0C8h], r12
0x1800099cd  lea     r8, [rsp+68h+arg_0]; unsigned __int64 *
0x1800099d2  mov     [rsp+68h+arg_0], r12
0x1800099d7  mov     edx, 104h; unsigned __int64
0x1800099dc  mov     rcx, r14; unsigned __int16 *
0x1800099df  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800099e4  mov     r15, [rsp+68h+arg_0]
0x1800099e9  mov     eax, 2
0x1800099ee  inc     r15
0x1800099f1  mul     r15
0x1800099f4  cmovb   rax, rbp
0x1800099f8  mov     rcx, rax; unsigned __int64
0x1800099fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009a00  mov     [rdi+0C8h], rax
0x180009a07  test    rax, rax
0x180009a0a  jnz     short loc_180009A16
0x180009a0c  mov     esi, 8007000Eh
0x180009a11  jmp     loc_180009B0D
0x180009a16  mov     r8, r14; unsigned __int16 *
0x180009a19  mov     rdx, r15; unsigned __int64
0x180009a1c  mov     rcx, rax; unsigned __int16 *
0x180009a1f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009a24  mov     r15d, 1
0x180009a2a  mov     [rdi+2428h], r12d
0x180009a31  mov     [rdi+18h], r12d
0x180009a35  mov     [rdi+100h], r12
0x180009a3c  mov     [rdi+140h], r12
0x180009a43  mov     [rdi+108h], r12
0x180009a4a  mov     [rdi+120h], r12
0x180009a51  mov     [rdi+1CC0h], r12
0x180009a58  mov     [rdi+150h], r12
0x180009a5f  cmp     [rdi+1Ch], r12d
0x180009a63  jz      short loc_180009A7A
0x180009a65  mov     rbp, [rdi+110h]
0x180009a6c  mov     [rdi+130h], rbp
0x180009a73  mov     [rdi+138h], rbp
0x180009a7a  mov     [rdi+128h], rbp
0x180009a81  mov     rcx, r12
0x180009a84  mov     rax, r12
0x180009a87  add     rcx, r15
0x180009a8a  mov     [rdi+rax+158h], r12
0x180009a92  mov     [rdi+rax+160h], r12
0x180009a9a  mov     [rdi+rax+168h], r12
0x180009aa2  mov     [rdi+rax+170h], r12d
0x180009aaa  mov     [rdi+rax+174h], r12w
0x180009ab3  lea     rax, [rax+30h]
0x180009ab7  cmp     rcx, 40h ; '@'
0x180009abb  jnz     short loc_180009A87
0x180009abd  mov     ebp, r12d
0x180009ac0  cmp     r12w, [rdi+20C8h]
0x180009ac8  jnb     short loc_180009AEE
0x180009aca  movzx   eax, bp
0x180009acd  mov     rcx, [rdi+rax*8+1EC8h]
0x180009ad5  mov     rax, [rcx]
0x180009ad8  mov     rax, [rax+8]
0x180009adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae1  add     bp, r15w
0x180009ae5  cmp     bp, [rdi+20C8h]
0x180009aec  jb      short loc_180009ACA
0x180009aee  mov     rcx, [rdi+20E0h]
0x180009af5  mov     [rdi+148h], r12
0x180009afc  test    rcx, rcx
0x180009aff  jz      short loc_180009B0D
0x180009b01  mov     rax, [rcx]
0x180009b04  mov     rax, [rax+38h]
0x180009b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b0d  mov     rcx, rbx; lpCriticalSection
0x180009b10  call    cs:__imp_LeaveCriticalSection
0x180009b16  lea     r11, [rsp+68h+var_28]
0x180009b1b  mov     eax, esi
0x180009b1d  mov     rbx, [r11+38h]
0x180009b21  mov     rbp, [r11+40h]
0x180009b25  mov     rsp, r11
0x180009b28  pop     r15
0x180009b2a  pop     r14
0x180009b2c  pop     r12
0x180009b2e  pop     rdi
0x180009b2f  pop     rsi
0x180009b30  retn
```
