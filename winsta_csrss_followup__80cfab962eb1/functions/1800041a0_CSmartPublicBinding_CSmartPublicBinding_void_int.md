# CSmartPublicBinding::CSmartPublicBinding(void *,int)

- ea: `0x1800041a0`
- end: `0x18000431d`
- name: `??0CSmartPublicBinding@@QEAA@PEAXH@Z`
- size: `381`
- prototype: `CSmartPublicBinding *__fastcall(CSmartPublicBinding *__hidden this, void *, int)`
- caller_count: `63`
- callee_count: `7`
- tags: ``

## callers

- `0x180001524`
- `0x180001d80`
- `0x180002114`
- `0x180002c00`
- `0x180002d34`
- `0x180009dec`
- `0x18000aac4`
- `0x18000d360`
- `0x18000f410`
- `0x180010bbc`
- `0x1800124ec`
- `0x180012b40`
- `0x18001369c`
- `0x1800210a0`
- `0x1800213c0`
- `0x1800214c0`
- `0x1800215e0`
- `0x1800216f8`
- `0x180021810`
- `0x180021af0`
- `0x180021e40`
- `0x180021fa4`
- `0x1800223c0`
- `0x180022740`
- `0x180022840`
- `0x180022970`
- `0x180022aa0`
- `0x180022bb8`
- `0x180022cb0`
- `0x180022ef0`
- `0x180023000`
- `0x1800230e0`
- `0x180023240`
- `0x1800233a0`
- `0x1800234e0`
- `0x180023690`
- `0x180023768`
- `0x1800239c0`
- `0x180023bc0`
- `0x180023d20`
- `0x180023e6c`
- `0x180023fc0`
- `0x180024240`
- `0x1800287d8`
- `0x1800294f0`
- `0x180029610`
- `0x1800299b0`
- `0x180029ad0`
- `0x180029de0`
- `0x180029ff0`

## callees

- `0x1800032b4`
- `0x1800041a0`
- `0x180004558`
- `0x180005b40`
- `0x1800066d0`
- `0x1800249e8`
- `0x180024a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800042fb`

## string_xrefs

- `0x1800042aa`: `StringCchCopy failed: %x`

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
        v8 = &dword_18003FF34;
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
0x1800041a0  mov     [rsp+arg_10], rbp
0x1800041a5  push    rdi
0x1800041a6  sub     rsp, 20h
0x1800041aa  xor     ebp, ebp
0x1800041ac  mov     [rcx], r8d
0x1800041af  mov     [rcx+4], ebp
0x1800041b2  mov     rdi, rcx
0x1800041b5  test    rdx, rdx
0x1800041b8  jnz     loc_1800042D6
0x1800041be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800041c5  mov     [rsp+28h+arg_0], rbx
0x1800041ca  mov     ecx, 40h ; '@'; unsigned __int64
0x1800041cf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800041d4  mov     rbx, rax
0x1800041d7  test    rax, rax
0x1800041da  jz      loc_1800042F2
0x1800041e0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800041e7  mov     [rax], rbp
0x1800041ea  mov     ecx, 2; unsigned __int64
0x1800041ef  mov     [rax+8], rbp
0x1800041f3  mov     [rax+10h], rbp
0x1800041f7  mov     [rax+18h], rbp
0x1800041fb  mov     [rax+20h], rbp
0x1800041ff  mov     [rax+28h], rbp
0x180004203  mov     qword ptr [rax+30h], 1
0x18000420b  mov     [rax+38h], rbp
0x18000420f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004214  mov     [rbx+28h], rax
0x180004218  mov     r9, rax
0x18000421b  test    rax, rax
0x18000421e  jz      short loc_180004281
0x180004220  mov     [rsp+28h+arg_8], rsi
0x180004225  lea     rdx, dword_18003FF34
0x18000422c  mov     ecx, 7FFFFFFEh
0x180004231  mov     r10d, 1
0x180004237  test    rcx, rcx
0x18000423a  jz      short loc_180004259
0x18000423c  movzx   eax, word ptr [rdx]
0x18000423f  test    ax, ax
0x180004242  jz      short loc_180004259
0x180004244  mov     [r9], ax
0x180004248  add     rdx, 2
0x18000424c  add     r9, 2
0x180004250  dec     rcx
0x180004253  sub     r10, 1
0x180004257  jnz     short loc_180004237
0x180004259  test    r10, r10
0x18000425c  lea     rcx, [r9-2]
0x180004260  mov     esi, 8007007Ah
0x180004265  cmovnz  rcx, r9
0x180004269  cmovnz  esi, ebp
0x18000426c  mov     [rcx], bp
0x18000426f  jz      short loc_1800042A0
0x180004271  cmp     [rbx+18h], rbp
0x180004275  jnz     short loc_18000427C
0x180004277  cmp     [rbx+30h], ebp
0x18000427a  jz      short loc_1800042BD
0x18000427c  mov     rsi, [rsp+28h+arg_8]
0x180004281  mov     [rdi+8], rbx
0x180004285  mov     dword ptr [rdi+4], 1
0x18000428c  mov     rbx, [rsp+28h+arg_0]
0x180004291  mov     rax, rdi
0x180004294  mov     rbp, [rsp+28h+arg_10]
0x180004299  add     rsp, 20h
0x18000429d  pop     rdi
0x18000429e  retn
0x1800042a0  mov     ecx, esi; int
0x1800042a2  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x1800042a7  mov     r8d, esi
0x1800042aa  lea     rdx, aStringcchcopyF; "StringCchCopy failed: %x"
0x1800042b1  mov     ecx, 8; int
0x1800042b6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800042bb  jmp     short loc_18000427C
0x1800042bd  mov     rcx, rbx; this
0x1800042c0  call    ?OpenSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::OpenSessionContextHandle(void)
0x1800042c5  cmp     eax, 800706BAh
0x1800042ca  jz      short loc_1800042E9
0x1800042cc  mov     rcx, rbx; this
0x1800042cf  call    ?CloseSessionContextHandle@CPublicBinding@@AEAAJXZ; CPublicBinding::CloseSessionContextHandle(void)
0x1800042d4  jmp     short loc_18000427C
0x1800042d6  mov     [rcx+8], rdx
0x1800042da  mov     rax, rdi
0x1800042dd  mov     rbp, [rsp+28h+arg_10]
0x1800042e2  add     rsp, 20h
0x1800042e6  pop     rdi
0x1800042e7  retn
0x1800042e9  mov     dword ptr [rbx+34h], 1
0x1800042f0  jmp     short loc_1800042CC
0x1800042f2  mov     ecx, 0Eh; dwErrCode
0x1800042f7  mov     [rdi+8], rbp
0x1800042fb  call    cs:__imp_SetLastError
0x180004302  nop     dword ptr [rax+rax+00h]
0x180004307  lea     rdx, aNewCpublicbind; "new CPublicBinding"
0x18000430e  mov     ecx, 8; int
0x180004313  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180004318  jmp     loc_18000428C
```
