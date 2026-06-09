# StripComments

- ea: `0x180001810`
- end: `0x18000192c`
- name: `StripComments`
- size: `284`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001490`

## callees

- `0x180001430`
- `0x180001460`
- `0x180001810`
- `0x180002560`
- `0x180002d70`
- `0x18000d196`

## import_xrefs

- `msvcrt!free` at `0x180001913`
- `msvcrt!free` at `0x180001913`
- `KERNEL32!SetLastError` at `0x1800018d8`
- `KERNEL32!SetLastError` at `0x1800018fc`
- `KERNEL32!SetLastError` at `0x1800018d8`
- `KERNEL32!SetLastError` at `0x1800018fc`

## pseudocode

```c
__int64 __fastcall StripComments(wchar_t *String1, unsigned int a2, unsigned __int16 **a3)
{
  __int64 v5; // rax
  unsigned int v6; // edx
  __int64 v7; // rbx
  const wchar_t *v8; // rbp
  __int64 v9; // rdi
  __int64 v10; // rax
  _QWORD *v11; // r8
  const wchar_t *v12; // rsi
  unsigned __int16 v13; // cx
  DWORD v14; // edi
  unsigned __int16 *v15; // rax
  unsigned int v16; // ebx
  void *Block[2]; // [rsp+20h] [rbp-68h] BYREF
  int v19; // [rsp+30h] [rbp-58h]

  Block[0] = 0;
  Block[1] = 0;
  v19 = 0;
  v5 = Comment(a2);
  v7 = -1;
  v8 = (const wchar_t *)v5;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v5 + 2 * v9) );
  v10 = EndSigBlock(v6);
  v12 = (const wchar_t *)v10;
  do
    ++v7;
  while ( *(_WORD *)(v10 + 2 * v7) );
  *v11 = 0;
  while ( wcsncmp_0(String1, v12, (unsigned int)v7) )
  {
    if ( wcsncmp_0(String1, v8, (unsigned int)v9) )
    {
      v14 = 0;
      SetLastError(0xBu);
LABEL_15:
      v16 = 0;
      SetLastError(v14);
      goto LABEL_17;
    }
    v13 = String1[(unsigned int)v9];
    for ( String1 += (unsigned int)v9; v13; ++String1 )
    {
      if ( v13 == 13 )
        break;
      BuildString::AppendCh((BuildString *)Block, v13);
      v13 = String1[1];
    }
  }
  v15 = BuildString::BstrReset((BuildString *)Block);
  *a3 = v15;
  if ( !v15 )
  {
    v14 = 8;
    goto LABEL_15;
  }
  v16 = 1;
LABEL_17:
  if ( Block[0] )
    free(Block[0]);
  return v16;
}

```

## disassembly

```asm
0x180001810  push    rbx
0x180001812  push    rbp
0x180001813  push    rsi
0x180001814  push    rdi
0x180001815  push    r12
0x180001817  push    r13
0x180001819  push    r14
0x18000181b  push    r15
0x18000181d  sub     rsp, 48h
0x180001821  xor     r13d, r13d
0x180001824  mov     r14, rcx
0x180001827  mov     ecx, edx
0x180001829  mov     [rsp+88h+Block], r13
0x18000182e  mov     [rsp+88h+var_60], r13
0x180001833  mov     r15, r8
0x180001836  mov     [rsp+88h+var_58], r13d
0x18000183b  call    Comment
0x180001840  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180001847  mov     rbp, rax
0x18000184a  mov     rdi, rbx
0x18000184d  nop     dword ptr [rax]
0x180001850  inc     rdi
0x180001853  cmp     [rax+rdi*2], r13w
0x180001858  jnz     short loc_180001850
0x18000185a  mov     ecx, edx
0x18000185c  call    EndSigBlock
0x180001861  mov     rsi, rax
0x180001864  inc     rbx
0x180001867  cmp     [rax+rbx*2], r13w
0x18000186c  jnz     short loc_180001864
0x18000186e  mov     [r8], r13
0x180001871  mov     r12d, 0Dh
0x180001877  mov     r8d, ebx; MaxCount
0x18000187a  mov     rdx, rsi; String2
0x18000187d  mov     rcx, r14; String1
0x180001880  call    wcsncmp_0
0x180001885  test    eax, eax
0x180001887  jz      short loc_1800018E0
0x180001889  mov     r8d, edi; MaxCount
0x18000188c  mov     rdx, rbp; String2
0x18000188f  mov     rcx, r14; String1
0x180001892  call    wcsncmp_0
0x180001897  test    eax, eax
0x180001899  jnz     short loc_1800018D0
0x18000189b  mov     eax, edi
0x18000189d  movzx   ecx, word ptr [r14+rax*2]
0x1800018a2  lea     r14, [r14+rax*2]
0x1800018a6  cmp     r13w, cx
0x1800018aa  jz      short loc_180001877
0x1800018ac  cmp     r12w, cx
0x1800018b0  jz      short loc_180001877
0x1800018b2  movzx   edx, cx; unsigned __int16
0x1800018b5  lea     rcx, [rsp+88h+Block]; this
0x1800018ba  call    ?AppendCh@BuildString@@QEAAXG@Z; BuildString::AppendCh(ushort)
0x1800018bf  movzx   ecx, word ptr [r14+2]
0x1800018c4  add     r14, 2
0x1800018c8  cmp     r13w, cx
0x1800018cc  jnz     short loc_1800018AC
0x1800018ce  jmp     short loc_180001877
0x1800018d0  mov     ecx, 0Bh; dwErrCode
0x1800018d5  mov     edi, r13d
0x1800018d8  call    cs:__imp_SetLastError
0x1800018de  jmp     short loc_1800018F7
0x1800018e0  lea     rcx, [rsp+88h+Block]; this
0x1800018e5  call    ?BstrReset@BuildString@@QEAAPEAGXZ; BuildString::BstrReset(void)
0x1800018ea  mov     [r15], rax
0x1800018ed  test    rax, rax
0x1800018f0  jnz     short loc_180001904
0x1800018f2  mov     edi, 8
0x1800018f7  mov     ecx, edi; dwErrCode
0x1800018f9  mov     ebx, r13d
0x1800018fc  call    cs:__imp_SetLastError
0x180001902  jmp     short loc_180001909
0x180001904  mov     ebx, 1
0x180001909  mov     rcx, [rsp+88h+Block]; Block
0x18000190e  test    rcx, rcx
0x180001911  jz      short loc_180001919
0x180001913  call    cs:__imp_free
0x180001919  mov     eax, ebx
0x18000191b  add     rsp, 48h
0x18000191f  pop     r15
0x180001921  pop     r14
0x180001923  pop     r13
0x180001925  pop     r12
0x180001927  pop     rdi
0x180001928  pop     rsi
0x180001929  pop     rbp
0x18000192a  pop     rbx
0x18000192b  retn
```
