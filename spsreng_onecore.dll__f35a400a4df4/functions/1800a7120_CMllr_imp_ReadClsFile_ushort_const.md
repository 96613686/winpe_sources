# CMllr_imp::ReadClsFile(ushort const *)

- ea: `0x1800a7120`
- end: `0x1800a733b`
- name: `?ReadClsFile@CMllr_imp@@AEAAJPEBG@Z`
- size: `539`
- prototype: `__int64 __fastcall(CMllr_imp *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800a6130`

## callees

- `0x1800034b0`
- `0x1800a6944`
- `0x1800a6a24`
- `0x1800a6b60`
- `0x1800a6cf4`
- `0x1800a6f94`
- `0x1800a7120`
- `0x1800a7564`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800a7168`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x1800a7168`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800a7212`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800a729b`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800a7212`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800a729b`
- `api-ms-win-crt-private-l1-1-0!_o_fgets` at `0x1800a71c5`
- `api-ms-win-crt-private-l1-1-0!_o_fgets` at `0x1800a71c5`

## pseudocode

```c
__int64 __fastcall CMllr_imp::ReadClsFile(struct CLND **this, const unsigned __int16 *a2)
{
  errno_t v3; // eax
  const unsigned __int16 *v4; // r8
  unsigned int v5; // ebx
  struct CLND *v6; // rdi
  struct CLND *v7; // rbx
  CMllr_imp *v8; // rcx
  int v9; // eax
  int v10; // r8d
  struct CLND *v12; // rax
  __int64 v13; // rdx
  __int16 v14; // r8
  int v15; // ecx
  struct CLND *v16; // rdx
  __int64 v17; // rax
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  struct CLND *v23; // [rsp+38h] [rbp-C8h] BYREF
  FILE *Stream; // [rsp+40h] [rbp-C0h] BYREF
  char v25[512]; // [rsp+50h] [rbp-B0h] BYREF

  Stream = 0;
  v22 = 0;
  v3 = _wfopen_s(&Stream, a2, L"r");
  if ( !Stream || v3 )
    return 2147500037LL;
  v5 = CMllr_imp::AllocClsBuf((CMllr_imp *)this, Stream, v4, v25, v19, &v22);
  if ( v5 )
  {
LABEL_13:
    if ( Stream )
      fclose(Stream);
    return v5;
  }
  v6 = this[8];
  this[11] = v6;
  *((_DWORD *)v6 + 9) &= ~1u;
  v7 = (struct CLND *)((char *)v6 + 64);
  v23 = (struct CLND *)((char *)v6 + 64);
  while ( _o_fgets(v25, 512, Stream) )
  {
    v9 = CMllr_imp::LineType(v8, v25);
    v10 = v9;
    if ( v9 > 6 )
    {
      if ( v9 != 7 && v9 != 8 && v9 != 9 )
      {
        if ( v9 != 10 )
          goto LABEL_12;
LABEL_22:
        v12 = v7;
        v7 = (struct CLND *)((char *)v7 + 64);
        v23 = v7;
        *((_QWORD *)v12 + 5) = v6;
        if ( v10 == 10 )
        {
          v5 = CMllr_imp::AddPseqClass((CMllr_imp *)this, v12, v25, &v23, v20, v21);
          if ( v5 )
            goto LABEL_13;
          v7 = v23;
        }
        else
        {
          v6 = v12;
        }
      }
    }
    else if ( v9 != 6 && v9 != 1 )
    {
      if ( v9 == 2 )
        goto LABEL_22;
      if ( v9 == 3 )
      {
        v6 = (struct CLND *)*((_QWORD *)v6 + 5);
        if ( !v6 )
          goto LABEL_12;
      }
      else if ( (unsigned int)(v9 - 4) >= 2 )
      {
        goto LABEL_12;
      }
    }
  }
  if ( v6 != this[11] )
  {
LABEL_12:
    v5 = -2147467259;
    goto LABEL_13;
  }
  fclose(Stream);
  CMllr_imp::AddImplicitCls((CMllr_imp *)this, &v23, v22);
  v13 = (v23 - this[8]) >> 6;
  *((_DWORD *)this + 25) = v13;
  CMllr_imp::SetChildCls((CMllr_imp *)this, v13);
  CMllr_imp::GroupAllSil((CMllr_imp *)this);
  v14 = 0;
  v15 = 0;
  for ( *((_DWORD *)this + 26) = 1; v15 < *((_DWORD *)this + 25); ++v15 )
  {
    v16 = this[8];
    v17 = (__int64)v15 << 6;
    v18 = *(_DWORD *)((char *)v16 + v17 + 56) == 0;
    *(_WORD *)((char *)v16 + v17) = -1;
    if ( v18 )
      *(_WORD *)((char *)v16 + v17) = v14++;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a7120  mov     [rsp-8+arg_10], rbx
0x1800a7125  push    rbp
0x1800a7126  push    rsi
0x1800a7127  push    rdi
0x1800a7128  lea     rbp, [rsp-160h]
0x1800a7130  sub     rsp, 260h
0x1800a7137  mov     rax, cs:__security_cookie
0x1800a713e  xor     rax, rsp
0x1800a7141  mov     [rbp+170h+var_20], rax
0x1800a7148  mov     rsi, rcx
0x1800a714b  mov     [rsp+270h+Stream], 0
0x1800a7154  lea     rcx, [rsp+270h+Stream]; Stream
0x1800a7159  mov     [rsp+270h+var_240], 0
0x1800a7161  lea     r8, aR; "r"
0x1800a7168  call    cs:__imp__wfopen_s
0x1800a716e  mov     rdx, [rsp+270h+Stream]; Stream
0x1800a7173  test    rdx, rdx
0x1800a7176  jz      loc_1800A7314
0x1800a717c  test    eax, eax
0x1800a717e  jnz     loc_1800A7314
0x1800a7184  lea     rax, [rsp+270h+var_240]
0x1800a7189  mov     rcx, rsi; this
0x1800a718c  lea     r9, [rsp+270h+var_220]; char *
0x1800a7191  mov     [rsp+270h+var_248], rax; int
0x1800a7196  call    ?AllocClsBuf@CMllr_imp@@AEAAJPEAU_iobuf@@PEBGPEADHPEAH@Z; CMllr_imp::AllocClsBuf(_iobuf *,ushort const *,char *,int,int *)
0x1800a719b  mov     ebx, eax
0x1800a719d  test    eax, eax
0x1800a719f  jnz     short loc_1800A7208
0x1800a71a1  mov     rdi, [rsi+40h]
0x1800a71a5  mov     [rsi+58h], rdi
0x1800a71a9  and     dword ptr [rdi+24h], 0FFFFFFFEh
0x1800a71ad  lea     rbx, [rdi+40h]
0x1800a71b1  mov     [rsp+270h+var_238], rbx
0x1800a71b6  mov     r8, [rsp+270h+Stream]
0x1800a71bb  lea     rcx, [rsp+270h+var_220]
0x1800a71c0  mov     edx, 200h
0x1800a71c5  call    cs:__imp__o_fgets
0x1800a71cb  test    rax, rax
0x1800a71ce  jz      loc_1800A728C
0x1800a71d4  lea     rdx, [rsp+270h+var_220]; char *
0x1800a71d9  call    ?LineType@CMllr_imp@@AEAAHPEBD@Z; CMllr_imp::LineType(char const *)
0x1800a71de  mov     r8d, eax
0x1800a71e1  cmp     eax, 6
0x1800a71e4  jg      short loc_1800A722A
0x1800a71e6  jz      short loc_1800A71B6
0x1800a71e8  mov     edx, eax
0x1800a71ea  sub     edx, 1
0x1800a71ed  jz      short loc_1800A71B6
0x1800a71ef  sub     edx, 1
0x1800a71f2  jz      short loc_1800A7249
0x1800a71f4  sub     edx, 1
0x1800a71f7  jz      short loc_1800A721F
0x1800a71f9  sub     edx, 1
0x1800a71fc  jz      short loc_1800A71B6
0x1800a71fe  cmp     edx, 1
0x1800a7201  jz      short loc_1800A71B6
0x1800a7203  mov     ebx, 80004005h
0x1800a7208  mov     rcx, [rsp+270h+Stream]; Stream
0x1800a720d  test    rcx, rcx
0x1800a7210  jz      short loc_1800A7218
0x1800a7212  call    cs:__imp_fclose
0x1800a7218  mov     eax, ebx
0x1800a721a  jmp     loc_1800A7319
0x1800a721f  mov     rdi, [rdi+28h]
0x1800a7223  test    rdi, rdi
0x1800a7226  jnz     short loc_1800A71B6
0x1800a7228  jmp     short loc_1800A7203
0x1800a722a  mov     ecx, r8d
0x1800a722d  sub     ecx, 7
0x1800a7230  jz      short loc_1800A71B6
0x1800a7232  sub     ecx, 1
0x1800a7235  jz      loc_1800A71B6
0x1800a723b  sub     ecx, 1
0x1800a723e  jz      loc_1800A71B6
0x1800a7244  cmp     ecx, 1
0x1800a7247  jnz     short loc_1800A7203
0x1800a7249  mov     rax, rbx
0x1800a724c  add     rbx, 40h ; '@'
0x1800a7250  mov     [rsp+270h+var_238], rbx
0x1800a7255  mov     [rax+28h], rdi
0x1800a7259  cmp     r8d, 0Ah
0x1800a725d  jnz     short loc_1800A7284
0x1800a725f  lea     r9, [rsp+270h+var_238]; struct CLND **
0x1800a7264  mov     rdx, rax; struct CLND *
0x1800a7267  lea     r8, [rsp+270h+var_220]; char *
0x1800a726c  mov     rcx, rsi; this
0x1800a726f  call    ?AddPseqClass@CMllr_imp@@AEAAJPEAUCLND@@PEBDPEAPEAU2@PEBGH@Z; CMllr_imp::AddPseqClass(CLND *,char const *,CLND * *,ushort const *,int)
0x1800a7274  mov     ebx, eax
0x1800a7276  test    eax, eax
0x1800a7278  jnz     short loc_1800A7208
0x1800a727a  mov     rbx, [rsp+270h+var_238]
0x1800a727f  jmp     loc_1800A71B6
0x1800a7284  mov     rdi, rax
0x1800a7287  jmp     loc_1800A71B6
0x1800a728c  cmp     rdi, [rsi+58h]
0x1800a7290  jnz     loc_1800A7203
0x1800a7296  mov     rcx, [rsp+270h+Stream]; Stream
0x1800a729b  call    cs:__imp_fclose
0x1800a72a1  mov     r8d, [rsp+270h+var_240]; int
0x1800a72a6  lea     rdx, [rsp+270h+var_238]; struct CLND **
0x1800a72ab  mov     rcx, rsi; this
0x1800a72ae  call    ?AddImplicitCls@CMllr_imp@@AEAAXPEAPEAUCLND@@H@Z; CMllr_imp::AddImplicitCls(CLND * *,int)
0x1800a72b3  mov     rdx, [rsp+270h+var_238]
0x1800a72b8  mov     rcx, rsi; this
0x1800a72bb  sub     rdx, [rsi+40h]
0x1800a72bf  sar     rdx, 6; int
0x1800a72c3  mov     [rsi+64h], edx
0x1800a72c6  call    ?SetChildCls@CMllr_imp@@AEAAXH@Z; CMllr_imp::SetChildCls(int)
0x1800a72cb  mov     rcx, rsi; this
0x1800a72ce  call    ?GroupAllSil@CMllr_imp@@AEAAXXZ; CMllr_imp::GroupAllSil(void)
0x1800a72d3  xor     r8d, r8d
0x1800a72d6  xor     ecx, ecx
0x1800a72d8  mov     r10d, 1
0x1800a72de  mov     [rsi+68h], r10d
0x1800a72e2  cmp     [rsi+64h], ecx
0x1800a72e5  jle     short loc_1800A7310
0x1800a72e7  mov     rdx, [rsi+40h]
0x1800a72eb  movsxd  rax, ecx
0x1800a72ee  shl     rax, 6
0x1800a72f2  cmp     dword ptr [rax+rdx+38h], 0
0x1800a72f7  mov     word ptr [rax+rdx], 0FFFFh
0x1800a72fd  jnz     short loc_1800A7308
0x1800a72ff  mov     [rax+rdx], r8w
0x1800a7304  add     r8w, r10w
0x1800a7308  add     ecx, r10d
0x1800a730b  cmp     ecx, [rsi+64h]
0x1800a730e  jl      short loc_1800A72E7
0x1800a7310  xor     eax, eax
0x1800a7312  jmp     short loc_1800A7319
0x1800a7314  mov     eax, 80004005h
0x1800a7319  mov     rcx, [rbp+170h+var_20]
0x1800a7320  xor     rcx, rsp; StackCookie
0x1800a7323  call    __security_check_cookie
0x1800a7328  mov     rbx, [rsp+270h+arg_10]
0x1800a7330  add     rsp, 260h
0x1800a7337  pop     rdi
0x1800a7338  pop     rsi
0x1800a7339  pop     rbp
0x1800a733a  retn
```
