# CSmartPublicBinding::CSmartPublicBinding(void *,int)

- ea: `0x180005c30`
- end: `0x180005da5`
- name: `??0CSmartPublicBinding@@QEAA@PEAXH@Z`
- size: `373`
- prototype: `CSmartPublicBinding *__fastcall(CSmartPublicBinding *__hidden this, void *, int)`
- caller_count: `63`
- callee_count: `7`
- tags: ``

## callers

- `0x1800011c0`
- `0x18000375c`
- `0x180003ba8`
- `0x180004114`
- `0x1800046ec`
- `0x180005194`
- `0x1800052bc`
- `0x18000ce54`
- `0x18000db70`
- `0x180011458`
- `0x1800119d4`
- `0x180011cb0`
- `0x180012828`
- `0x18001f9b0`
- `0x18001fcb0`
- `0x18001fda0`
- `0x18001feb0`
- `0x18001ffbc`
- `0x1800200c0`
- `0x180020380`
- `0x1800206a0`
- `0x1800207f4`
- `0x180020c00`
- `0x180020f50`
- `0x180021050`
- `0x180021170`
- `0x180021290`
- `0x18002139c`
- `0x180021480`
- `0x1800216a0`
- `0x1800217a0`
- `0x180021870`
- `0x1800219c0`
- `0x180021b20`
- `0x180021c50`
- `0x180021de8`
- `0x180021eb4`
- `0x180022100`
- `0x1800222d0`
- `0x180022430`
- `0x18002256c`
- `0x1800226c0`
- `0x180022920`
- `0x180026d68`
- `0x180027a20`
- `0x180027b30`
- `0x180027e90`
- `0x180027fa0`
- `0x180028290`
- `0x180028470`

## callees

- `0x180005374`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008340`
- `0x1800230b8`
- `0x1800230ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005d89`

## string_xrefs

- `0x180005d39`: `StringCchCopy failed: %x`

## pseudocode

```c
CSmartPublicBinding *__fastcall CSmartPublicBinding::CSmartPublicBinding(CSmartPublicBinding *this, void *a2, int a3)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _WORD *v6; // rax
  _WORD *v7; // r9
  int *v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r10
  _WORD *v11; // rcx
  int v12; // esi

  *(_DWORD *)this = a3;
  *((_DWORD *)this + 1) = 0;
  if ( a2 )
  {
    *((_QWORD *)this + 1) = a2;
    return this;
  }
  else
  {
    v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v5 = v4;
    if ( v4 )
    {
      *v4 = 0;
      v4[1] = 0;
      v4[2] = 0;
      v4[3] = 0;
      v4[4] = 0;
      v4[5] = 0;
      v4[6] = 1;
      v4[7] = 0;
      v6 = operator new[](2u, (const struct std::nothrow_t *)&std::nothrow);
      v5[5] = v6;
      v7 = v6;
      if ( v6 )
      {
        v8 = &dword_18003D0CC;
        v9 = 2147483646;
        v10 = 1;
        do
        {
          if ( !v9 )
            break;
          if ( !*(_WORD *)v8 )
            break;
          *v7 = *(_WORD *)v8;
          v8 = (int *)((char *)v8 + 2);
          ++v7;
          --v9;
          --v10;
        }
        while ( v10 );
        v11 = v7 - 1;
        v12 = -2147024774;
        if ( v10 )
        {
          v11 = v7;
          v12 = 0;
        }
        *v11 = 0;
        if ( v10 )
        {
          if ( !v5[3] && !*((_DWORD *)v5 + 12) )
          {
            if ( (unsigned int)CPublicBinding::OpenSessionContextHandle((RPC_BINDING_HANDLE *)v5) == -2147023174 )
              *((_DWORD *)v5 + 13) = 1;
            CPublicBinding::CloseSessionContextHandle((CPublicBinding *)v5);
          }
        }
        else
        {
          ConvertHRESULT2WIN32(v12);
          _DbgPrintMessage(8, "StringCchCopy failed: %x", v12);
        }
      }
      *((_QWORD *)this + 1) = v5;
      *((_DWORD *)this + 1) = 1;
    }
    else
    {
      *((_QWORD *)this + 1) = 0;
      SetLastError(0xEu);
      _DbgPrintMessage(8, "new CPublicBinding");
    }
    return this;
  }
}

```

## disassembly

```asm
0x180005c30  mov     [rsp+arg_10], rbp
0x180005c35  push    rdi
0x180005c36  sub     rsp, 20h
0x180005c3a  xor     ebp, ebp
0x180005c3c  mov     [rcx], r8d
0x180005c3f  mov     [rcx+4], ebp
0x180005c42  mov     rdi, rcx
0x180005c45  test    rdx, rdx
0x180005c48  jnz     loc_180005D65
0x180005c4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c55  mov     [rsp+28h+arg_0], rbx
0x180005c5a  mov     ecx, 40h ; '@'; unsigned __int64
0x180005c5f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005c64  mov     rbx, rax
0x180005c67  test    rax, rax
0x180005c6a  jz      loc_180005D80
0x180005c70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c77  mov     [rax], rbp
0x180005c7a  mov     ecx, 2; unsigned __int64
0x180005c7f  mov     [rax+8], rbp
0x180005c83  mov     [rax+10h], rbp
0x180005c87  mov     [rax+18h], rbp
0x180005c8b  mov     [rax+20h], rbp
0x180005c8f  mov     [rax+28h], rbp
0x180005c93  mov     qword ptr [rax+30h], 1
0x180005c9b  mov     [rax+38h], rbp
0x180005c9f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180005ca4  mov     [rbx+28h], rax
0x180005ca8  mov     r9, rax
0x180005cab  test    rax, rax
0x180005cae  jz      short loc_180005D11
0x180005cb0  mov     [rsp+28h+arg_8], rsi
0x180005cb5  lea     rdx, dword_18003D0CC
0x180005cbc  mov     ecx, 7FFFFFFEh
0x180005cc1  mov     r10d, 1
0x180005cc7  test    rcx, rcx
0x180005cca  jz      short loc_180005CE9
0x180005ccc  movzx   eax, word ptr [rdx]
0x180005ccf  test    ax, ax
0x180005cd2  jz      short loc_180005CE9
0x180005cd4  mov     [r9], ax
0x180005cd8  add     rdx, 2
0x180005cdc  add     r9, 2
0x180005ce0  dec     rcx
0x180005ce3  sub     r10, 1
0x180005ce7  jnz     short loc_180005CC7
0x180005ce9  test    r10, r10
0x180005cec  lea     rcx, [r9-2]
0x180005cf0  mov     esi, 8007007Ah
0x180005cf5  cmovnz  rcx, r9
0x180005cf9  cmovnz  esi, ebp
0x180005cfc  mov     [rcx], bp
0x180005cff  jz      short loc_180005D2F
0x180005d01  cmp     [rbx+18h], rbp
0x180005d05  jnz     short loc_180005D0C
0x180005d07  cmp     [rbx+30h], ebp
0x180005d0a  jz      short loc_180005D4C
0x180005d0c  mov     rsi, [rsp+28h+arg_8]
0x180005d11  mov     [rdi+8], rbx
0x180005d15  mov     dword ptr [rdi+4], 1
0x180005d1c  mov     rbx, [rsp+28h+arg_0]
0x180005d21  mov     rax, rdi
0x180005d24  mov     rbp, [rsp+28h+arg_10]
0x180005d29  add     rsp, 20h
0x180005d2d  pop     rdi
0x180005d2e  retn
0x180005d2f  mov     ecx, esi; int
0x180005d31  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180005d36  mov     r8d, esi
0x180005d39  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x180005d40  mov     ecx, 8; int
0x180005d45  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005d4a  jmp     short loc_180005D0C
0x180005d4c  mov     rcx, rbx; this
0x180005d4f  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x180005d54  cmp     eax, 800706BAh
0x180005d59  jz      short loc_180005D77
0x180005d5b  mov     rcx, rbx; this
0x180005d5e  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x180005d63  jmp     short loc_180005D0C
0x180005d65  mov     [rcx+8], rdx
0x180005d69  mov     rax, rdi
0x180005d6c  mov     rbp, [rsp+28h+arg_10]
0x180005d71  add     rsp, 20h
0x180005d75  pop     rdi
0x180005d76  retn
0x180005d77  mov     dword ptr [rbx+34h], 1
0x180005d7e  jmp     short loc_180005D5B
0x180005d80  mov     ecx, 0Eh; dwErrCode
0x180005d85  mov     [rdi+8], rbp
0x180005d89  call    cs:__imp_SetLastError
0x180005d8f  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x180005d96  mov     ecx, 8; int
0x180005d9b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180005da0  jmp     loc_180005D1C
```
