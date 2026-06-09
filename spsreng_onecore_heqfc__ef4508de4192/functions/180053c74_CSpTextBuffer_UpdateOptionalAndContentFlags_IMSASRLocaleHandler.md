# CSpTextBuffer::UpdateOptionalAndContentFlags(IMSASRLocaleHandler *)

- ea: `0x180053c74`
- end: `0x180053dfc`
- name: `?UpdateOptionalAndContentFlags@CSpTextBuffer@@QEAAXPEAUIMSASRLocaleHandler@@@Z`
- size: `392`
- prototype: `void __fastcall(CSpTextBuffer *__hidden this, struct IMSASRLocaleHandler *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180053658`

## callees

- `0x180052258`
- `0x180053c74`
- `0x180053f68`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dc1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053dc1`

## pseudocode

```c
void __fastcall CSpTextBuffer::UpdateOptionalAndContentFlags(CSpTextBuffer *this, struct IMSASRLocaleHandler *a2)
{
  __int64 i; // rsi
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int16 *v7; // rax
  int v8; // eax
  _QWORD *v9; // rcx
  int v10; // eax
  __int64 j; // rdi
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  LPVOID v13; // [rsp+38h] [rbp-8h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v15; // [rsp+80h] [rbp+40h] BYREF
  int v16; // [rsp+88h] [rbp+48h] BYREF

  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 4); i = (unsigned int)(i + 1) )
  {
    v5 = *((_QWORD *)this + 1);
    if ( (*(_DWORD *)(v5 + 24 * i + 4) & 0x18) == 8 )
    {
      v14 = 0;
      (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(v5 + 24 * i + 16) + 160LL))(
        *(_QWORD *)(v5 + 24 * i + 16),
        &v14);
      *(_DWORD *)(*((_QWORD *)this + 1) + 24 * i + 4) = *(_DWORD *)(*((_QWORD *)this + 1) + 24 * i + 4) & 0xFFFFFFEF
                                                      | (16 * (v14 & 1));
    }
    if ( (unsigned int)CSpTextBuffer::fContentRequired(this) )
    {
      v6 = *((_QWORD *)this + 1);
      v14 = 1;
      if ( (*(_BYTE *)(v6 + 24 * i + 4) & 8) != 0 )
      {
        v15 = 0;
        pv = 0;
        v13 = 0;
        v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID *, LPVOID *))(**(_QWORD **)(v6 + 24 * i + 16)
                                                                                   + 40LL))(
               *(_QWORD *)(v6 + 24 * i + 16),
               &v15,
               &pv,
               &v13);
        v9 = pv;
        if ( v8 >= 0 )
        {
          v10 = 0;
          v16 = 0;
          for ( j = 0; v9; j = (unsigned int)(j + 1) )
          {
            if ( (unsigned int)j >= v15 )
              break;
            (*(void (__fastcall **)(struct IMSASRLocaleHandler *, _QWORD, int *))(*(_QWORD *)a2 + 192LL))(
              a2,
              v9[j],
              &v16);
            v10 = v16;
            v9 = pv;
            if ( v16 )
              break;
          }
          v14 = v10;
        }
        if ( v9 )
          CoTaskMemFree(v9);
        if ( v13 )
          CoTaskMemFree(v13);
      }
      else
      {
        v7 = CSpTextBuffer::NormalizedWord(this, i);
        (*(void (__fastcall **)(struct IMSASRLocaleHandler *, unsigned __int16 *, int *))(*(_QWORD *)a2 + 192LL))(
          a2,
          v7,
          &v14);
      }
      *(_DWORD *)(*((_QWORD *)this + 1) + 24 * i + 8) = *(_DWORD *)(*((_QWORD *)this + 1) + 24 * i + 8) & 0xFFFFFFFE
                                                      | v14 & 1;
    }
  }
}

```

## disassembly

```asm
0x180053c74  mov     [rsp-28h+arg_8], rbx
0x180053c79  push    rbp
0x180053c7a  push    rsi
0x180053c7b  push    rdi
0x180053c7c  push    r14
0x180053c7e  push    r15
0x180053c80  mov     rbp, rsp
0x180053c83  sub     rsp, 40h
0x180053c87  xor     esi, esi
0x180053c89  mov     r15, rdx
0x180053c8c  mov     rbx, rcx
0x180053c8f  cmp     [rcx+10h], esi
0x180053c92  jbe     loc_180053DEB
0x180053c98  mov     rcx, [rbx+8]
0x180053c9c  lea     r14, [rsi+rsi*2]
0x180053ca0  mov     eax, [rcx+r14*8+4]
0x180053ca5  and     al, 18h
0x180053ca7  cmp     al, 8
0x180053ca9  jnz     short loc_180053CE6
0x180053cab  mov     [rbp+arg_0], 0
0x180053cb2  lea     rdx, [rbp+arg_0]
0x180053cb6  mov     rcx, [rcx+r14*8+10h]
0x180053cbb  mov     rax, [rcx]
0x180053cbe  mov     rax, [rax+0A0h]
0x180053cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cca  mov     rdx, [rbx+8]
0x180053cce  mov     ecx, [rbp+arg_0]
0x180053cd1  and     ecx, 1
0x180053cd4  shl     ecx, 4
0x180053cd7  mov     eax, [rdx+r14*8+4]
0x180053cdc  and     eax, 0FFFFFFEFh
0x180053cdf  or      ecx, eax
0x180053ce1  mov     [rdx+r14*8+4], ecx
0x180053ce6  mov     rcx, rbx; this
0x180053ce9  call    ?fContentRequired@CSpTextBuffer@@QEAAHXZ; CSpTextBuffer::fContentRequired(void)
0x180053cee  test    eax, eax
0x180053cf0  jz      loc_180053DE0
0x180053cf6  mov     rcx, [rbx+8]
0x180053cfa  mov     [rbp+arg_0], 1
0x180053d01  test    byte ptr [rcx+r14*8+4], 8
0x180053d07  jnz     short loc_180053D34
0x180053d09  mov     edx, esi; int
0x180053d0b  mov     rcx, rbx; this
0x180053d0e  call    ?NormalizedWord@CSpTextBuffer@@QEAAPEAGH@Z; CSpTextBuffer::NormalizedWord(int)
0x180053d13  mov     rcx, [r15]
0x180053d16  lea     r8, [rbp+arg_0]
0x180053d1a  mov     rdx, rax
0x180053d1d  mov     r9, [rcx+0C0h]
0x180053d24  mov     rcx, r15
0x180053d27  mov     rax, r9
0x180053d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d2f  jmp     loc_180053DC7
0x180053d34  mov     [rbp+arg_10], 0
0x180053d3b  lea     r9, [rbp+var_8]
0x180053d3f  mov     [rbp+pv], 0
0x180053d47  lea     r8, [rbp+pv]
0x180053d4b  mov     [rbp+var_8], 0
0x180053d53  lea     rdx, [rbp+arg_10]
0x180053d57  mov     rcx, [rcx+r14*8+10h]
0x180053d5c  mov     rax, [rcx]
0x180053d5f  mov     rax, [rax+28h]
0x180053d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d68  mov     rcx, [rbp+pv]
0x180053d6c  test    eax, eax
0x180053d6e  js      short loc_180053DAD
0x180053d70  xor     eax, eax
0x180053d72  mov     [rbp+arg_18], eax
0x180053d75  xor     edi, edi
0x180053d77  jmp     short loc_180053DA5
0x180053d79  cmp     edi, [rbp+arg_10]
0x180053d7c  jnb     short loc_180053DAA
0x180053d7e  mov     rax, [r15]
0x180053d81  lea     r8, [rbp+arg_18]
0x180053d85  mov     rdx, [rcx+rdi*8]
0x180053d89  mov     rcx, r15
0x180053d8c  mov     rax, [rax+0C0h]
0x180053d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d98  mov     eax, [rbp+arg_18]
0x180053d9b  mov     rcx, [rbp+pv]; pv
0x180053d9f  test    eax, eax
0x180053da1  jnz     short loc_180053DAA
0x180053da3  inc     edi
0x180053da5  test    rcx, rcx
0x180053da8  jnz     short loc_180053D79
0x180053daa  mov     [rbp+arg_0], eax
0x180053dad  test    rcx, rcx
0x180053db0  jz      short loc_180053DB8
0x180053db2  call    cs:__imp_CoTaskMemFree
0x180053db8  mov     rcx, [rbp+var_8]; pv
0x180053dbc  test    rcx, rcx
0x180053dbf  jz      short loc_180053DC7
0x180053dc1  call    cs:__imp_CoTaskMemFree
0x180053dc7  mov     rdx, [rbx+8]
0x180053dcb  mov     ecx, [rbp+arg_0]
0x180053dce  and     ecx, 1
0x180053dd1  mov     eax, [rdx+r14*8+8]
0x180053dd6  and     eax, 0FFFFFFFEh
0x180053dd9  or      ecx, eax
0x180053ddb  mov     [rdx+r14*8+8], ecx
0x180053de0  inc     esi
0x180053de2  cmp     esi, [rbx+10h]
0x180053de5  jb      loc_180053C98
0x180053deb  mov     rbx, [rsp+40h+arg_8]
0x180053df0  add     rsp, 40h
0x180053df4  pop     r15
0x180053df6  pop     r14
0x180053df8  pop     rdi
0x180053df9  pop     rsi
0x180053dfa  pop     rbp
0x180053dfb  retn
```
