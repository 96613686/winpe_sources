# XCodeReplaceAt(CEsExec *,CXVariant *,int)

- ea: `0x1007e5e00`
- end: `0x1007e6242`
- name: `?XCodeReplaceAt@@YAXPEAVCEsExec@@PEAVCXVariant@@H@Z`
- size: `1090`
- prototype: `void __fastcall(struct CEsExec *, struct CXVariant *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1007e6270`
- `0x1007e62b0`

## callees

- `0x100401170`
- `0x1007e5e00`

## import_xrefs

- `sqldk!??3@YAXPEAX_K@Z` at `0x1007e61cd`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1007e61cd`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007e5e91`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007e5f56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007e6033`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007e5e91`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007e5f56`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1007e6033`

## string_xrefs

- `0x1007e600e`: `WRITE`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall XCodeReplaceAt(struct CEsExec *a1, struct CXVariant *a2, int a3)
{
  __int64 v6; // rcx
  unsigned __int8 *v7; // r12
  char v8; // al
  __int64 v9; // rbx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r13
  __int64 v13; // rdi
  unsigned __int64 v14; // r14
  void *v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // r12
  __int64 v18; // rdx
  __int64 v19; // rdi
  char v20; // [rsp+30h] [rbp-A9h]
  unsigned int v21; // [rsp+34h] [rbp-A5h] BYREF
  __int64 v22; // [rsp+38h] [rbp-A1h]
  __int64 v23; // [rsp+40h] [rbp-99h]
  __int64 v24; // [rsp+48h] [rbp-91h]
  struct CEsExec *v25; // [rsp+50h] [rbp-89h] BYREF
  int v26; // [rsp+58h] [rbp-81h]
  void *v27; // [rsp+60h] [rbp-79h]
  void **v28; // [rsp+68h] [rbp-71h] BYREF
  int v29; // [rsp+70h] [rbp-69h]
  int v30; // [rsp+74h] [rbp-65h]
  char v31; // [rsp+78h] [rbp-61h]
  void *v32; // [rsp+80h] [rbp-59h]
  int v33; // [rsp+88h] [rbp-51h]
  __int64 v34; // [rsp+90h] [rbp-49h]
  char v35[8]; // [rsp+98h] [rbp-41h] BYREF
  _BYTE v36[16]; // [rsp+A0h] [rbp-39h] BYREF
  unsigned __int64 v37; // [rsp+B0h] [rbp-29h]

  v34 = -2;
  v26 = a3;
  v25 = a1;
  v6 = *((_QWORD *)a1 + 4);
  v7 = (unsigned __int8 *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 168LL) + 32LL * *(unsigned __int16 *)(v6 + 24));
  v8 = *(_BYTE *)(v6 + 16);
  v20 = v8;
  if ( *((_BYTE *)a2 + 64) != 3 && *((__int64 *)a2 + 9) < 0 || *((_BYTE *)a2 + 96) != 3 && *((__int64 *)a2 + 13) < 0 )
  {
    ex_raise(5, 83, 16, 0);
    return;
  }
  if ( *(_BYTE *)a2 != 3 )
  {
    v22 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a2 + 1) + 8LL))(*((_QWORD *)a2 + 1), v8 != 0 ? 6 : 0);
    v22 = v9;
    (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, v36, 0);
    v10 = v37;
    v23 = v37;
    if ( *((_BYTE *)a2 + 64) == 3 )
    {
      v11 = v37;
    }
    else
    {
      v11 = 2LL * *((_QWORD *)a2 + 9);
      if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *v7)) )
        v11 = *((_QWORD *)a2 + 9);
      if ( v11 > v37 )
      {
        ex_raise(5, 82, 16, 0);
LABEL_43:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        return;
      }
    }
    v12 = 0;
    v13 = 0;
    v24 = 0;
    v27 = 0;
    if ( *((_BYTE *)a2 + 32) == 3 )
    {
      if ( *((_BYTE *)a2 + 64) == 3 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 160LL))(v9);
        goto LABEL_41;
      }
      v14 = 0;
    }
    else
    {
      v15 = (void *)*((_QWORD *)a2 + 5);
      v27 = v15;
      if ( a3 )
      {
        v13 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v15 + 8LL))(v15, 0);
        v24 = v13;
        (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v13 + 72LL))(v13, v36, 0);
        v12 = v37;
        v14 = 0;
        v27 = 0;
        if ( *((_BYTE *)a2 + 32) == 3 )
          goto LABEL_27;
        v10 = v23;
      }
      else
      {
        v12 = *((unsigned int *)a2 + 12);
      }
      v14 = 0;
      if ( *((_BYTE *)a2 + 64) != 3 )
      {
        v14 = v10 - v11;
        if ( *((_BYTE *)a2 + 96) != 3 )
        {
          v16 = 2LL * *((_QWORD *)a2 + 13);
          if ( !*((_BYTE *)&CTypeInfo::sxm_rgfIsUnicode + *((unsigned __int8 *)&xsm_rgOrdFromXvt + *v7)) )
            v16 = *((_QWORD *)a2 + 13);
          if ( v16 < v14 )
            v14 = v16;
        }
      }
    }
LABEL_27:
    if ( v23 + v12 - v14 > 0x7FFFFFFF )
    {
      ex_raise(5, 99, 16, 2, 10, L"WRITE");
LABEL_41:
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_43;
    }
    v17 = 0;
    v21 = 0;
    if ( !v20 )
    {
      v18 = *(unsigned __int16 *)(*((_QWORD *)v25 + 4) + 18LL);
      v17 = *(_QWORD *)(*((_QWORD *)v25 + 7) + 8 * v18);
      v21 = *(unsigned __int16 *)(*(_QWORD *)(*((_QWORD *)v25 + 2) + 32LL) + 2 * v18);
      (*(void (__fastcall **)(_QWORD, __int64, unsigned int *, struct CEsExec *, _DWORD))(**((_QWORD **)v25 + 10) + 96LL))(
        *((_QWORD *)v25 + 10),
        v17,
        &v21,
        v25,
        0);
      v23 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 8LL))(v17, 0);
      v23 = v19;
      (*(void (__fastcall **)(__int64, _QWORD, __int64, _QWORD, char *))(*(_QWORD *)v19 + 192LL))(v19, 0, v9, 0, v35);
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v23 = 0;
      v22 = v19;
    }
    if ( *((_BYTE *)a2 + 32) == 3 )
    {
      _mm_lfence();
      v9 = v22;
      (*(void (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v22 + 48LL))(v22, v11);
    }
    else
    {
      v25 = 0;
      _mm_lfence();
      if ( v26 )
      {
        v9 = v22;
        v13 = v24;
        (*(void (__fastcall **)(__int64, unsigned __int64, __int64, unsigned __int64, struct CEsExec **))(*(_QWORD *)v22 + 192LL))(
          v22,
          v11,
          v24,
          v14,
          &v25);
        goto LABEL_39;
      }
      v28 = &CShortConstLockBytesSS::`vftable';
      v30 = 1;
      v31 = 0;
      v32 = v27;
      v33 = v12;
      v29 = 1;
      v9 = v22;
      (*(void (__fastcall **)(__int64, unsigned __int64, void ***, unsigned __int64, struct CEsExec **))(*(_QWORD *)v22 + 192LL))(
        v22,
        v11,
        &v28,
        v14,
        &v25);
      v28 = &CShortConstLockBytesSS::`vftable';
      if ( v31 )
        operator delete(v32, 1u);
      v28 = &CConstLockBytesSS::`vftable';
    }
    v13 = v24;
LABEL_39:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 160LL))(v9);
    if ( !v20 )
    {
      *((_QWORD *)a2 + 1) = v17;
      *((_QWORD *)a2 + 2) = v21;
    }
    goto LABEL_41;
  }
}

```

## disassembly

```asm
0x1007e5e00  push    rbp
0x1007e5e02  push    rsi
0x1007e5e03  push    rdi
0x1007e5e04  push    r12
0x1007e5e06  push    r13
0x1007e5e08  push    r14
0x1007e5e0a  push    r15
0x1007e5e0c  lea     rbp, [rsp-27h]
0x1007e5e11  sub     rsp, 100h
0x1007e5e18  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x1007e5e20  mov     [rsp+130h+arg_10], rbx
0x1007e5e28  mov     rax, cs:__security_cookie
0x1007e5e2f  xor     rax, rsp
0x1007e5e32  mov     [rbp+57h+var_40], rax
0x1007e5e36  mov     r14d, r8d
0x1007e5e39  mov     [rsp+130h+var_D8], r8d
0x1007e5e3e  mov     rsi, rdx
0x1007e5e41  mov     rax, rcx
0x1007e5e44  mov     [rsp+130h+var_E0], rcx
0x1007e5e49  mov     rcx, [rcx+20h]
0x1007e5e4d  movzx   r12d, word ptr [rcx+18h]
0x1007e5e52  shl     r12, 5
0x1007e5e56  mov     rax, [rax+10h]
0x1007e5e5a  add     r12, [rax+0A8h]
0x1007e5e61  movzx   eax, byte ptr [rcx+10h]
0x1007e5e65  mov     [rsp+130h+var_100], al
0x1007e5e69  cmp     byte ptr [rdx+40h], 3
0x1007e5e6d  jz      short loc_1007E5E76
0x1007e5e6f  cmp     qword ptr [rdx+48h], 0
0x1007e5e74  jl      short loc_1007E5E83
0x1007e5e76  cmp     byte ptr [rdx+60h], 3
0x1007e5e7a  jz      short loc_1007E5E9C
0x1007e5e7c  cmp     qword ptr [rdx+68h], 0
0x1007e5e81  jge     short loc_1007E5E9C
0x1007e5e83  xor     r9d, r9d
0x1007e5e86  lea     edx, [r9+53h]
0x1007e5e8a  lea     ecx, [rdx-4Eh]
0x1007e5e8d  lea     r8d, [r9+10h]
0x1007e5e91  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007e5e97  jmp     loc_1007E621B
0x1007e5e9c  cmp     byte ptr [rdx], 3
0x1007e5e9f  jz      loc_1007E621B
0x1007e5ea5  mov     [rsp+130h+var_F8], 0
0x1007e5eae  mov     rcx, [rdx+8]
0x1007e5eb2  mov     r8, [rcx]
0x1007e5eb5  neg     al
0x1007e5eb7  sbb     edx, edx
0x1007e5eb9  and     edx, 6
0x1007e5ebc  call    qword ptr [r8+8]
0x1007e5ec0  mov     rbx, rax
0x1007e5ec3  mov     [rsp+130h+var_F8], rax
0x1007e5ec8  mov     rax, [rax]
0x1007e5ecb  xor     r8d, r8d
0x1007e5ece  lea     rdx, [rbp+57h+var_90]
0x1007e5ed2  mov     rcx, rbx
0x1007e5ed5  call    qword ptr [rax+48h]
0x1007e5ed8  mov     r8, [rbp+57h+var_80]
0x1007e5edc  mov     [rsp+130h+var_F0], r8
0x1007e5ee1  lea     r10, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1007e5ee8  cmp     byte ptr [rsi+40h], 3
0x1007e5eec  jnz     short loc_1007E5F20
0x1007e5eee  mov     r15, r8
0x1007e5ef1  xor     r9d, r9d
0x1007e5ef4  mov     r13d, r9d
0x1007e5ef7  mov     edi, r9d
0x1007e5efa  mov     [rsp+130h+var_E8], r9
0x1007e5eff  mov     [rbp+57h+var_D0], r9
0x1007e5f03  cmp     byte ptr [rsi+20h], 3
0x1007e5f07  jnz     short loc_1007E5F69
0x1007e5f09  cmp     byte ptr [rsi+40h], 3
0x1007e5f0d  jnz     short loc_1007E5F61
0x1007e5f0f  mov     rax, [rbx]
0x1007e5f12  mov     rcx, rbx
0x1007e5f15  call    qword ptr [rax+0A0h]
0x1007e5f1b  jmp     loc_1007E6203
0x1007e5f20  mov     rdx, [rsi+48h]
0x1007e5f24  movzx   eax, byte ptr [r12]
0x1007e5f29  movzx   ecx, byte ptr [rax+r10+45AE60h]
0x1007e5f32  lea     r15, [rdx+rdx]
0x1007e5f36  cmp     byte ptr [rcx+r10+45AF60h], 0
0x1007e5f3f  cmovz   r15, rdx
0x1007e5f43  cmp     r15, r8
0x1007e5f46  jbe     short loc_1007E5EF1
0x1007e5f48  xor     r9d, r9d
0x1007e5f4b  lea     edx, [r9+52h]
0x1007e5f4f  lea     ecx, [rdx-4Dh]
0x1007e5f52  lea     r8d, [r9+10h]
0x1007e5f56  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007e5f5c  jmp     loc_1007E6212
0x1007e5f61  mov     r14, r9
0x1007e5f64  jmp     loc_1007E5FFB
0x1007e5f69  mov     rcx, [rsi+28h]
0x1007e5f6d  mov     [rbp+57h+var_D0], rcx
0x1007e5f71  test    r14d, r14d
0x1007e5f74  jz      short loc_1007E5FB8
0x1007e5f76  mov     rax, [rcx]
0x1007e5f79  xor     edx, edx
0x1007e5f7b  call    qword ptr [rax+8]
0x1007e5f7e  mov     rdi, rax
0x1007e5f81  mov     [rsp+130h+var_E8], rax
0x1007e5f86  mov     rax, [rax]
0x1007e5f89  xor     r8d, r8d
0x1007e5f8c  lea     rdx, [rbp+57h+var_90]
0x1007e5f90  mov     rcx, rdi
0x1007e5f93  call    qword ptr [rax+48h]
0x1007e5f96  mov     r13, [rbp+57h+var_80]
0x1007e5f9a  xor     r9d, r9d
0x1007e5f9d  mov     r14d, r9d
0x1007e5fa0  mov     [rbp+57h+var_D0], r9
0x1007e5fa4  cmp     byte ptr [rsi+20h], 3
0x1007e5fa8  jz      short loc_1007E5FFB
0x1007e5faa  mov     r8, [rsp+130h+var_F0]
0x1007e5faf  lea     r10, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x1007e5fb6  jmp     short loc_1007E5FBC
0x1007e5fb8  mov     r13d, [rsi+30h]
0x1007e5fbc  mov     r14, r9
0x1007e5fbf  cmp     byte ptr [rsi+40h], 3
0x1007e5fc3  jz      short loc_1007E5FFB
0x1007e5fc5  mov     r14, r8
0x1007e5fc8  sub     r14, r15
0x1007e5fcb  cmp     byte ptr [rsi+60h], 3
0x1007e5fcf  jz      short loc_1007E5FFB
0x1007e5fd1  mov     rdx, [rsi+68h]
0x1007e5fd5  movzx   eax, byte ptr [r12]
0x1007e5fda  movzx   ecx, byte ptr [rax+r10+45AE60h]
0x1007e5fe3  lea     rax, [rdx+rdx]
0x1007e5fe7  cmp     byte ptr [rcx+r10+45AF60h], 0
0x1007e5ff0  cmovz   rax, rdx
0x1007e5ff4  cmp     rax, r14
0x1007e5ff7  cmovb   r14, rax
0x1007e5ffb  mov     rax, r13
0x1007e5ffe  sub     rax, r14
0x1007e6001  add     rax, [rsp+130h+var_F0]
0x1007e6006  cmp     rax, 7FFFFFFFh
0x1007e600c  jbe     short loc_1007E603E
0x1007e600e  lea     rax, aWrite; "WRITE"
0x1007e6015  mov     [rsp+130h+var_108], rax
0x1007e601a  mov     [rsp+130h+var_110], 0Ah
0x1007e6023  mov     edx, 63h ; 'c'
0x1007e6028  lea     ecx, [rdx-5Eh]
0x1007e602b  lea     r9d, [rdx-61h]
0x1007e602f  lea     r8d, [rdx-53h]
0x1007e6033  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x1007e6039  jmp     loc_1007E6203
0x1007e603e  mov     r12, r9
0x1007e6041  mov     [rsp+130h+var_FC], r9d
0x1007e6046  cmp     [rsp+130h+var_100], 0
0x1007e604b  jnz     loc_1007E60EB
0x1007e6051  mov     r8, [rsp+130h+var_E0]
0x1007e6056  mov     rax, [r8+20h]
0x1007e605a  movzx   edx, word ptr [rax+12h]
0x1007e605e  mov     rax, [r8+38h]
0x1007e6062  mov     r12, [rax+rdx*8]
0x1007e6066  mov     rax, [r8+10h]
0x1007e606a  mov     rcx, [rax+20h]
0x1007e606e  movzx   eax, word ptr [rcx+rdx*2]
0x1007e6072  mov     [rsp+130h+var_FC], eax
0x1007e6076  mov     rcx, [r8+50h]
0x1007e607a  mov     rax, [rcx]
0x1007e607d  mov     dword ptr [rsp+130h+var_110], r9d
0x1007e6082  mov     r9, r8
0x1007e6085  lea     r8, [rsp+130h+var_FC]
0x1007e608a  mov     rdx, r12
0x1007e608d  call    qword ptr [rax+60h]
0x1007e6090  mov     [rsp+130h+var_F0], 0
0x1007e6099  mov     rax, [r12]
0x1007e609d  xor     edx, edx
0x1007e609f  mov     rcx, r12
0x1007e60a2  call    qword ptr [rax+8]
0x1007e60a5  mov     rdi, rax
0x1007e60a8  mov     [rsp+130h+var_F0], rax
0x1007e60ad  mov     r10, [rax]
0x1007e60b0  lea     rax, [rbp+57h+var_98]
0x1007e60b4  mov     [rsp+130h+var_110], rax
0x1007e60b9  xor     r9d, r9d
0x1007e60bc  mov     r8, rbx
0x1007e60bf  xor     edx, edx
0x1007e60c1  mov     rcx, rdi
0x1007e60c4  call    qword ptr [r10+0C0h]
0x1007e60cb  mov     [rsp+130h+var_F8], 0
0x1007e60d4  mov     r8, [rbx]
0x1007e60d7  mov     rcx, rbx
0x1007e60da  call    qword ptr [r8+10h]
0x1007e60de  xor     r9d, r9d
0x1007e60e1  mov     [rsp+130h+var_F0], r9
0x1007e60e6  mov     [rsp+130h+var_F8], rdi
0x1007e60eb  cmp     byte ptr [rsi+20h], 3
0x1007e60ef  jnz     short loc_1007E610A
0x1007e60f1  lfence
0x1007e60f4  mov     rbx, [rsp+130h+var_F8]
0x1007e60f9  mov     rax, [rbx]
0x1007e60fc  mov     rdx, r15
0x1007e60ff  mov     rcx, rbx
0x1007e6102  call    qword ptr [rax+30h]
0x1007e6105  jmp     loc_1007E61DF
0x1007e610a  mov     [rsp+130h+var_E0], r9
0x1007e610f  lfence
0x1007e6112  cmp     [rsp+130h+var_D8], 0
0x1007e6117  jz      short loc_1007E6147
0x1007e6119  mov     rbx, [rsp+130h+var_F8]
0x1007e611e  mov     rax, [rbx]
0x1007e6121  lea     rcx, [rsp+130h+var_E0]
0x1007e6126  mov     [rsp+130h+var_110], rcx
0x1007e612b  mov     r9, r14
0x1007e612e  mov     rdi, [rsp+130h+var_E8]
0x1007e6133  mov     r8, rdi
0x1007e6136  mov     rdx, r15
0x1007e6139  mov     rcx, rbx
0x1007e613c  call    qword ptr [rax+0C0h]
0x1007e6142  jmp     loc_1007E61E4
0x1007e6147  lea     rax, ??_7IConstLockBytesSS@@6B@; const IConstLockBytesSS::`vftable'
0x1007e614e  mov     [rbp+57h+var_C8], rax
0x1007e6152  lea     rax, ??_7CConstLockBytesSS@@6B@; const CConstLockBytesSS::`vftable'
0x1007e6159  mov     [rbp+57h+var_C8], rax
0x1007e615d  mov     [rbp+57h+var_C0], 1
0x1007e6164  mov     [rbp+57h+var_BC], 1
0x1007e616b  lea     rdi, ??_7CShortConstLockBytesSS@@6B@; const CShortConstLockBytesSS::`vftable'
0x1007e6172  mov     [rbp+57h+var_C8], rdi
0x1007e6176  mov     [rbp+57h+var_BC], 1
0x1007e617d  mov     [rbp+57h+var_B8], 0
0x1007e6181  mov     rax, [rbp+57h+var_D0]
0x1007e6185  mov     [rbp+57h+var_B0], rax
0x1007e6189  mov     [rbp+57h+var_A8], r13d
0x1007e618d  mov     [rbp+57h+var_C0], 1
0x1007e6194  mov     rbx, [rsp+130h+var_F8]
0x1007e6199  mov     rax, [rbx]
0x1007e619c  lea     rcx, [rsp+130h+var_E0]
0x1007e61a1  mov     [rsp+130h+var_110], rcx
0x1007e61a6  mov     r9, r14
0x1007e61a9  lea     r8, [rbp+57h+var_C8]
0x1007e61ad  mov     rdx, r15
0x1007e61b0  mov     rcx, rbx
0x1007e61b3  call    qword ptr [rax+0C0h]
0x1007e61b9  nop
0x1007e61ba  mov     [rbp+57h+var_C8], rdi
0x1007e61be  cmp     [rbp+57h+var_B8], 0
0x1007e61c2  jz      short loc_1007E61D4
0x1007e61c4  mov     edx, 1
0x1007e61c9  mov     rcx, [rbp+57h+var_B0]
0x1007e61cd  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1007e61d3  nop
0x1007e61d4  lea     rax, ??_7CConstLockBytesSS@@6B@; const CConstLockBytesSS::`vftable'
0x1007e61db  mov     [rbp+57h+var_C8], rax
0x1007e61df  mov     rdi, [rsp+130h+var_E8]
0x1007e61e4  mov     rax, [rbx]
0x1007e61e7  mov     rcx, rbx
0x1007e61ea  call    qword ptr [rax+0A0h]
0x1007e61f0  cmp     [rsp+130h+var_100], 0
0x1007e61f5  jnz     short loc_1007E6203
0x1007e61f7  mov     [rsi+8], r12
0x1007e61fb  mov     eax, [rsp+130h+var_FC]
0x1007e61ff  mov     [rsi+10h], rax
0x1007e6203  test    rdi, rdi
0x1007e6206  jz      short loc_1007E6212
0x1007e6208  mov     rax, [rdi]
0x1007e620b  mov     rcx, rdi
0x1007e620e  call    qword ptr [rax+10h]
0x1007e6211  nop
0x1007e6212  mov     rax, [rbx]
0x1007e6215  mov     rcx, rbx
0x1007e6218  call    qword ptr [rax+10h]
0x1007e621b  mov     rcx, [rbp+57h+var_40]
0x1007e621f  xor     rcx, rsp; StackCookie
0x1007e6222  call    __security_check_cookie
0x1007e6227  mov     rbx, [rsp+130h+arg_10]
0x1007e622f  add     rsp, 100h
0x1007e6236  pop     r15
0x1007e6238  pop     r14
0x1007e623a  pop     r13
0x1007e623c  pop     r12
0x1007e623e  pop     rdi
0x1007e623f  pop     rsi
0x1007e6240  pop     rbp
0x1007e6241  retn
```
