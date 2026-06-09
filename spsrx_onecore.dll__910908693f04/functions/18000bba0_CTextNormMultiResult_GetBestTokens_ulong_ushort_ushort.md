# CTextNormMultiResult::GetBestTokens(ulong *,ushort * * *,ushort * *)

- ea: `0x18000bba0`
- end: `0x18000bccd`
- name: `?GetBestTokens@CTextNormMultiResult@@UEAAJPEAKPEAPEAPEAGPEAPEAG@Z`
- size: `301`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, unsigned int *, unsigned __int16 ***, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002ec0`
- `0x18000bba0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bc4e`

## pseudocode

```c
__int64 __fastcall CTextNormMultiResult::GetBestTokens(
        CTextNormMultiResult *this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        unsigned __int16 **a4)
{
  int v8; // ebx
  __int64 v9; // rdi
  int v10; // r15d
  unsigned int v11; // edx
  int v12; // ecx
  unsigned int v13; // r15d
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // r14
  __int64 v17; // rdx
  unsigned int v18; // r8d
  __int64 v19; // rax

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = (*(__int64 (__fastcall **)(CTextNormMultiResult *, __int64))(*(_QWORD *)this + 184LL))(this, 1);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CTextNormMultiResult *, unsigned __int16 **))(*(_QWORD *)this + 24LL))(this, a4);
    if ( v8 >= 0 )
    {
      if ( *a4 )
      {
        v9 = -1;
        do
          ++v9;
        while ( (*a4)[v9] );
        if ( (_DWORD)v9 )
        {
          v10 = 0;
          v11 = 0;
          do
          {
            v12 = v10 + 1;
            if ( (*a4)[v11] != 32 )
              v12 = v10;
            ++v11;
            v10 = v12;
          }
          while ( v11 < (unsigned int)v9 );
          v13 = v12 + 1;
          v14 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)(v12 + 1));
          v15 = v14;
          if ( !v14 )
            return 2147942414LL;
          memset_0(v14, 0, 8LL * v13);
          v17 = 0;
          *v15 = *a4;
          v18 = 1;
          do
          {
            if ( v18 >= v13 )
              break;
            if ( (*a4)[v17] == 32 )
            {
              (*a4)[v17] = 0;
              v19 = v18++;
              v15[v19] = &(*a4)[v17 + 1];
            }
            v17 = (unsigned int)(v17 + 1);
          }
          while ( (unsigned int)v17 < (unsigned int)v9 );
          *a2 = v13;
          *a3 = v15;
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bba0  push    rbx
0x18000bba2  push    rbp
0x18000bba3  push    rsi
0x18000bba4  push    rdi
0x18000bba5  push    r12
0x18000bba7  push    r13
0x18000bba9  push    r14
0x18000bbab  push    r15
0x18000bbad  sub     rsp, 28h
0x18000bbb1  xor     ebp, ebp
0x18000bbb3  mov     r13, rdx
0x18000bbb6  mov     [rdx], ebp
0x18000bbb8  mov     rsi, r9
0x18000bbbb  mov     [r8], rbp
0x18000bbbe  mov     r12, r8
0x18000bbc1  mov     [r9], rbp
0x18000bbc4  mov     rdi, rcx
0x18000bbc7  mov     rax, [rcx]
0x18000bbca  lea     edx, [rbp+1]
0x18000bbcd  mov     rax, [rax+0B8h]
0x18000bbd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbd9  mov     ebx, eax
0x18000bbdb  test    eax, eax
0x18000bbdd  js      loc_18000BCBA
0x18000bbe3  mov     rax, [rdi]
0x18000bbe6  mov     rdx, rsi
0x18000bbe9  mov     rcx, rdi
0x18000bbec  mov     rax, [rax+18h]
0x18000bbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf5  mov     ebx, eax
0x18000bbf7  test    eax, eax
0x18000bbf9  js      loc_18000BCBA
0x18000bbff  mov     rax, [rsi]
0x18000bc02  test    rax, rax
0x18000bc05  jz      loc_18000BCBA
0x18000bc0b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000bc0f  inc     rdi
0x18000bc12  cmp     [rax+rdi*2], bp
0x18000bc16  jnz     short loc_18000BC0F
0x18000bc18  test    edi, edi
0x18000bc1a  jz      loc_18000BCBA
0x18000bc20  mov     r15d, ebp
0x18000bc23  mov     edx, ebp
0x18000bc25  mov     r8, rax
0x18000bc28  mov     eax, edx
0x18000bc2a  lea     ecx, [r15+1]
0x18000bc2e  cmp     word ptr [r8+rax*2], 20h ; ' '
0x18000bc34  cmovnz  ecx, r15d
0x18000bc38  inc     edx
0x18000bc3a  mov     r15d, ecx
0x18000bc3d  cmp     edx, edi
0x18000bc3f  jb      short loc_18000BC28
0x18000bc41  inc     r15d
0x18000bc44  mov     ebp, r15d
0x18000bc47  shl     rbp, 3
0x18000bc4b  mov     rcx, rbp; cb
0x18000bc4e  call    cs:__imp_CoTaskMemAlloc
0x18000bc54  mov     r14, rax
0x18000bc57  test    rax, rax
0x18000bc5a  jnz     short loc_18000BC63
0x18000bc5c  mov     eax, 8007000Eh
0x18000bc61  jmp     short loc_18000BCBC
0x18000bc63  mov     r8, rbp; Size
0x18000bc66  xor     edx, edx; Val
0x18000bc68  mov     rcx, r14; void *
0x18000bc6b  call    memset_0
0x18000bc70  mov     rax, [rsi]
0x18000bc73  xor     edx, edx
0x18000bc75  mov     [r14], rax
0x18000bc78  lea     r8d, [rdx+1]
0x18000bc7c  test    edi, edi
0x18000bc7e  jz      short loc_18000BCB2
0x18000bc80  cmp     r8d, r15d
0x18000bc83  jnb     short loc_18000BCB2
0x18000bc85  mov     r9, [rsi]
0x18000bc88  cmp     word ptr [r9+rdx*2], 20h ; ' '
0x18000bc8e  jnz     short loc_18000BCAC
0x18000bc90  xor     eax, eax
0x18000bc92  mov     [r9+rdx*2], ax
0x18000bc97  mov     rax, [rsi]
0x18000bc9a  add     rax, 2
0x18000bc9e  lea     rcx, [rax+rdx*2]
0x18000bca2  mov     eax, r8d
0x18000bca5  inc     r8d
0x18000bca8  mov     [r14+rax*8], rcx
0x18000bcac  inc     edx
0x18000bcae  cmp     edx, edi
0x18000bcb0  jb      short loc_18000BC80
0x18000bcb2  mov     [r13+0], r15d
0x18000bcb6  mov     [r12], r14
0x18000bcba  mov     eax, ebx
0x18000bcbc  add     rsp, 28h
0x18000bcc0  pop     r15
0x18000bcc2  pop     r14
0x18000bcc4  pop     r13
0x18000bcc6  pop     r12
0x18000bcc8  pop     rdi
0x18000bcc9  pop     rsi
0x18000bcca  pop     rbp
0x18000bccb  pop     rbx
0x18000bccc  retn
```
