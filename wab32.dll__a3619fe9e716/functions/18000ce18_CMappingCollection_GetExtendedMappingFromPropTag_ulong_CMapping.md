# CMappingCollection::GetExtendedMappingFromPropTag(ulong,CMapping * *)

- ea: `0x18000ce18`
- end: `0x18000cfee`
- name: `?GetExtendedMappingFromPropTag@CMappingCollection@@QEAAJKPEAPEAVCMapping@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(CMappingCollection *__hidden this, unsigned int, struct CMapping **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180011b5c`
- `0x180011bd8`

## callees

- `0x180001610`
- `0x18000161c`
- `0x180009428`
- `0x18000ce18`
- `0x180093010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000ce31`
- `KERNEL32!EnterCriticalSection` at `0x18000ce31`
- `KERNEL32!LeaveCriticalSection` at `0x18000cfb6`
- `KERNEL32!LeaveCriticalSection` at `0x18000cfb6`
- `iertutil!__imp_DPA_Create` at `0x18000ce46`
- `iertutil!__imp_DPA_Create` at `0x18000ce46`
- `iertutil!__imp_DPA_GetPtr` at `0x18000ce63`
- `iertutil!__imp_DPA_GetPtr` at `0x18000ce63`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000cf8c`
- `iertutil!__imp_DPA_InsertPtr` at `0x18000cf8c`

## pseudocode

```c
__int64 __fastcall CMappingCollection::GetExtendedMappingFromPropTag(
        CMappingCollection *this,
        int a2,
        struct CMapping **a3)
{
  unsigned __int16 *v5; // rsi
  struct _DPA *v6; // rax
  unsigned int i; // ebx
  struct CMapping *Ptr; // rax
  _QWORD *v9; // rbx
  int v10; // edi
  _QWORD *v11; // rax
  void **v12; // rax
  unsigned __int16 *v13; // rax

  v5 = 0;
  EnterCriticalSection(&CriticalSection);
  v6 = hdpa;
  if ( !hdpa )
  {
    v6 = DPA_Create(10);
    hdpa = v6;
    if ( !v6 )
      goto LABEL_30;
  }
  for ( i = 0; ; ++i )
  {
    Ptr = (struct CMapping *)DPA_GetPtr(v6, i);
    if ( !Ptr )
      break;
    if ( *((_DWORD *)Ptr + 6) == a2 )
    {
      *a3 = Ptr;
LABEL_8:
      v9 = 0;
      v10 = 0;
      goto LABEL_32;
    }
    v6 = hdpa;
  }
  v11 = operator new(0x28u);
  v9 = v11;
  if ( !v11 )
  {
LABEL_30:
    v9 = 0;
    goto LABEL_31;
  }
  v11[1] = 0;
  v11[2] = 0;
  *((_DWORD *)v11 + 6) = 0;
  *v11 = &CTimerCallback::`vftable';
  v11[4] = 0;
  switch ( (unsigned __int16)a2 )
  {
    case 0x1Fu:
      v12 = &off_1800A9C98;
      break;
    case 0x40u:
      v12 = &off_1800A9CC0;
      break;
    case 0x48u:
      v12 = &off_1800A9D10;
      break;
    default:
      if ( (unsigned __int16)a2 != 258 )
      {
        switch ( (unsigned __int16)a2 )
        {
          case 0x101Eu:
          case 0x101Fu:
            v12 = &off_1800A9D38;
            goto LABEL_25;
          case 0x1040u:
            v12 = &off_1800A9D60;
            goto LABEL_25;
          case 0x1102u:
            v12 = &off_1800A9D88;
            goto LABEL_25;
        }
      }
      v12 = &off_1800A9CE8;
      break;
  }
LABEL_25:
  *(_OWORD *)v9 = *(_OWORD *)v12;
  *((_OWORD *)v9 + 1) = *((_OWORD *)v12 + 1);
  v9[4] = v12[4];
  v13 = (unsigned __int16 *)operator new(0x80u);
  v5 = v13;
  if ( !v13 )
  {
LABEL_31:
    v10 = -2147024882;
    goto LABEL_32;
  }
  v10 = StringCchPrintfW(v13, 0x40u, L"%s0x%X", L"[MSWABMAPI]PropTag", a2);
  if ( v10 >= 0 )
  {
    *((_DWORD *)v9 + 6) = a2;
    v9[4] = v5;
    if ( DPA_InsertPtr(hdpa, 0x7FFFFFFF, v9) != -1 )
    {
      v5 = 0;
      *a3 = (struct CMapping *)v9;
      goto LABEL_8;
    }
    v10 = -2147467259;
  }
LABEL_32:
  LeaveCriticalSection(&CriticalSection);
  if ( v5 )
    operator delete(v5);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v9)(v9, 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ce18  push    rbx
0x18000ce1a  push    rbp
0x18000ce1b  push    rsi
0x18000ce1c  push    rdi
0x18000ce1d  push    r14
0x18000ce1f  sub     rsp, 30h
0x18000ce23  lea     rcx, CriticalSection; lpCriticalSection
0x18000ce2a  mov     r14, r8
0x18000ce2d  mov     ebp, edx
0x18000ce2f  xor     esi, esi
0x18000ce31  call    cs:__imp_EnterCriticalSection
0x18000ce37  mov     rax, cs:hdpa
0x18000ce3e  test    rax, rax
0x18000ce41  jnz     short loc_18000CE5C
0x18000ce43  lea     ecx, [rsi+0Ah]; cItemGrow
0x18000ce46  call    cs:__imp_DPA_Create
0x18000ce4c  mov     cs:hdpa, rax
0x18000ce53  test    rax, rax
0x18000ce56  jz      loc_18000CFA8
0x18000ce5c  xor     ebx, ebx
0x18000ce5e  mov     edx, ebx; i
0x18000ce60  mov     rcx, rax; hdpa
0x18000ce63  call    cs:__imp_DPA_GetPtr
0x18000ce69  test    rax, rax
0x18000ce6c  jz      short loc_18000CE8A
0x18000ce6e  cmp     [rax+18h], ebp
0x18000ce71  jz      short loc_18000CE7E
0x18000ce73  mov     rax, cs:hdpa
0x18000ce7a  inc     ebx
0x18000ce7c  jmp     short loc_18000CE5E
0x18000ce7e  mov     [r14], rax
0x18000ce81  xor     ebx, ebx
0x18000ce83  xor     edi, edi
0x18000ce85  jmp     loc_18000CFAF
0x18000ce8a  mov     ecx, 28h ; '('; Size
0x18000ce8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce94  mov     rbx, rax
0x18000ce97  test    rax, rax
0x18000ce9a  jz      loc_18000CFA8
0x18000cea0  mov     [rax+8], rsi
0x18000cea4  mov     [rax+10h], rsi
0x18000cea8  mov     [rax+18h], esi
0x18000ceab  lea     rax, ??_7CTimerCallback@@6B@; const CTimerCallback::`vftable'
0x18000ceb2  mov     [rbx], rax
0x18000ceb5  movzx   eax, bp
0x18000ceb8  mov     [rbx+20h], rsi
0x18000cebc  sub     eax, 1Fh
0x18000cebf  jz      short loc_18000CF20
0x18000cec1  sub     eax, 21h ; '!'
0x18000cec4  jz      short loc_18000CF17
0x18000cec6  sub     eax, 8
0x18000cec9  jz      short loc_18000CF0E
0x18000cecb  sub     eax, 0BAh
0x18000ced0  jz      short loc_18000CF05
0x18000ced2  sub     eax, 0F1Ch
0x18000ced7  jz      short loc_18000CEFC
0x18000ced9  sub     eax, 1
0x18000cedc  jz      short loc_18000CEFC
0x18000cede  sub     eax, 21h ; '!'
0x18000cee1  jz      short loc_18000CEF3
0x18000cee3  cmp     eax, 0C2h
0x18000cee8  jnz     short loc_18000CF05
0x18000ceea  lea     rax, off_1800A9D88
0x18000cef1  jmp     short loc_18000CF27
0x18000cef3  lea     rax, off_1800A9D60
0x18000cefa  jmp     short loc_18000CF27
0x18000cefc  lea     rax, off_1800A9D38
0x18000cf03  jmp     short loc_18000CF27
0x18000cf05  lea     rax, off_1800A9CE8
0x18000cf0c  jmp     short loc_18000CF27
0x18000cf0e  lea     rax, off_1800A9D10
0x18000cf15  jmp     short loc_18000CF27
0x18000cf17  lea     rax, off_1800A9CC0
0x18000cf1e  jmp     short loc_18000CF27
0x18000cf20  lea     rax, off_1800A9C98
0x18000cf27  movups  xmm0, xmmword ptr [rax]
0x18000cf2a  mov     ecx, 80h; Size
0x18000cf2f  movups  xmmword ptr [rbx], xmm0
0x18000cf32  movups  xmm1, xmmword ptr [rax+10h]
0x18000cf36  movups  xmmword ptr [rbx+10h], xmm1
0x18000cf3a  movsd   xmm0, qword ptr [rax+20h]
0x18000cf3f  movsd   qword ptr [rbx+20h], xmm0
0x18000cf44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cf49  mov     rsi, rax
0x18000cf4c  test    rax, rax
0x18000cf4f  jz      short loc_18000CFAA
0x18000cf51  lea     r9, aMswabmapiPropt; "[MSWABMAPI]PropTag"
0x18000cf58  mov     [rsp+58h+var_38], ebp
0x18000cf5c  lea     r8, aS0xX; "%s0x%X"
0x18000cf63  mov     edx, 40h ; '@'; unsigned __int64
0x18000cf68  mov     rcx, rax; unsigned __int16 *
0x18000cf6b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000cf70  mov     edi, eax
0x18000cf72  test    eax, eax
0x18000cf74  js      short loc_18000CFAF
0x18000cf76  mov     [rbx+18h], ebp
0x18000cf79  mov     r8, rbx; p
0x18000cf7c  mov     [rbx+20h], rsi
0x18000cf80  mov     edx, 7FFFFFFFh; i
0x18000cf85  mov     rcx, cs:hdpa; hdpa
0x18000cf8c  call    cs:__imp_DPA_InsertPtr
0x18000cf92  cmp     eax, 0FFFFFFFFh
0x18000cf95  jnz     short loc_18000CF9E
0x18000cf97  mov     edi, 80004005h
0x18000cf9c  jmp     short loc_18000CFAF
0x18000cf9e  xor     esi, esi
0x18000cfa0  mov     [r14], rbx
0x18000cfa3  jmp     loc_18000CE81
0x18000cfa8  xor     ebx, ebx
0x18000cfaa  mov     edi, 8007000Eh
0x18000cfaf  lea     rcx, CriticalSection; lpCriticalSection
0x18000cfb6  call    cs:__imp_LeaveCriticalSection
0x18000cfbc  test    rsi, rsi
0x18000cfbf  jz      short loc_18000CFC9
0x18000cfc1  mov     rcx, rsi; Block
0x18000cfc4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cfc9  test    rbx, rbx
0x18000cfcc  jz      short loc_18000CFE1
0x18000cfce  mov     rax, [rbx]
0x18000cfd1  mov     edx, 1
0x18000cfd6  mov     rcx, rbx
0x18000cfd9  mov     rax, [rax]
0x18000cfdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe1  mov     eax, edi
0x18000cfe3  add     rsp, 30h
0x18000cfe7  pop     r14
0x18000cfe9  pop     rdi
0x18000cfea  pop     rsi
0x18000cfeb  pop     rbp
0x18000cfec  pop     rbx
0x18000cfed  retn
```
