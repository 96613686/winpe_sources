# CEnumLocalAccounts::Next(ulong,IPropertyStore * *,ulong *)

- ea: `0x180011150`
- end: `0x1800112fe`
- name: `?Next@CEnumLocalAccounts@@UEAAJKPEAPEAUIPropertyStore@@PEAK@Z`
- size: `430`
- prototype: `__int64 __fastcall(CEnumLocalAccounts *__hidden this, unsigned int, struct IPropertyStore **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800037e0`
- `0x18000b290`
- `0x18000b9e0`
- `0x180011150`
- `0x180013130`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001128b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001128b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001120d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001120d`

## pseudocode

```c
__int64 __fastcall CEnumLocalAccounts::Next(
        CEnumLocalAccounts *this,
        __int64 a2,
        struct IPropertyStore **a3,
        unsigned int *a4)
{
  int v5; // r12d
  unsigned int v6; // ecx
  void *v7; // r15
  unsigned int *v8; // rsi
  unsigned int v9; // edx
  int v10; // ebx
  LPVOID v11; // r13
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  struct _UNICODE_STRING *v15; // r14
  SIZE_T v16; // rbx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  int v19; // r8d
  LPVOID v21; // [rsp+30h] [rbp-48h] BYREF
  struct IPropertyStore *v22; // [rsp+38h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+80h] [rbp+8h] BYREF
  struct IPropertyStore **v24; // [rsp+90h] [rbp+18h]
  unsigned int *v25; // [rsp+98h] [rbp+20h]

  v25 = a4;
  v24 = a3;
  v5 = 0;
  v6 = *((_DWORD *)this + 3);
  v7 = 0;
  v22 = 0;
  v8 = a4;
  v9 = v6 + *((_DWORD *)this + 6);
  v21 = 0;
  if ( *((_DWORD *)this + 10) >= v9 )
    goto LABEL_23;
  if ( *((_DWORD *)this + 10) >= v6 )
  {
    v14 = CSGetBuiltInDomainSid(&v21);
    v7 = v21;
    v10 = v14;
    v11 = v21;
    v12 = 3LL * (unsigned int)(*((_DWORD *)this + 10) - *((_DWORD *)this + 3));
    v13 = *((_QWORD *)this + 4);
  }
  else
  {
    v10 = CSGetAccountDomainSid(&pv);
    v11 = 0;
    v12 = 3LL * *((unsigned int *)this + 10);
    v13 = *((_QWORD *)this + 2);
  }
  if ( v10 >= 0 )
  {
    if ( v11 )
    {
      v15 = (struct _UNICODE_STRING *)(v13 + 8 * v12 + 8);
      if ( v13 + 8 * v12 != -8 )
      {
        v16 = (unsigned int)v15->Length + 2;
        v17 = (unsigned __int16 *)CoTaskMemAlloc(v16);
        v18 = v17;
        if ( v17 )
        {
          v10 = CopyUstrToPstr(v15, v17, v16);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(CEnumLocalAccounts *, LPVOID, unsigned __int16 *, struct IPropertyStore **))(*(_QWORD *)this + 72LL))(
                    this,
                    v11,
                    v18,
                    &v22);
            if ( v10 < 0 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v19, (_DWORD)v18, v10);
              }
            }
            else
            {
              ++*((_DWORD *)this + 10);
              v5 = 1;
            }
          }
          CoTaskMemFree(v18);
        }
        else
        {
          v10 = -2147024882;
        }
        v8 = v25;
      }
    }
  }
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v5 )
  {
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  else
  {
LABEL_23:
    v10 = 1;
  }
  *v24 = v22;
  if ( v8 )
    *v8 = v5;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011150  mov     rax, rsp
0x180011153  mov     [rax+10h], rbx
0x180011157  mov     [rax+20h], r9
0x18001115b  mov     [rax+18h], r8
0x18001115f  push    rbp
0x180011160  push    rsi
0x180011161  push    rdi
0x180011162  push    r12
0x180011164  push    r13
0x180011166  push    r14
0x180011168  push    r15
0x18001116a  sub     rsp, 40h
0x18001116e  mov     rdi, rcx
0x180011171  xor     r12d, r12d
0x180011174  mov     ecx, [rcx+0Ch]
0x180011177  xor     ebp, ebp
0x180011179  xor     r15d, r15d
0x18001117c  mov     [rax-40h], r12
0x180011180  mov     rsi, r9
0x180011183  mov     [rax+8], rbp
0x180011187  mov     edx, [rdi+18h]
0x18001118a  add     edx, ecx
0x18001118c  mov     [rax-48h], r15
0x180011190  cmp     [rdi+28h], edx
0x180011193  jnb     loc_1800112C7
0x180011199  cmp     [rdi+28h], ecx
0x18001119c  jnb     short loc_1800111C1
0x18001119e  lea     rcx, [rax+8]
0x1800111a2  call    CSGetAccountDomainSid
0x1800111a7  mov     rbp, [rsp+78h+pv]
0x1800111af  mov     ebx, eax
0x1800111b1  mov     eax, [rdi+28h]
0x1800111b4  mov     r13, rbp
0x1800111b7  lea     rcx, [rax+rax*2]
0x1800111bb  mov     rax, [rdi+10h]
0x1800111bf  jmp     short loc_1800111E3
0x1800111c1  lea     rcx, [rsp+78h+var_48]
0x1800111c6  call    CSGetBuiltInDomainSid
0x1800111cb  mov     r15, [rsp+78h+var_48]
0x1800111d0  mov     ebx, eax
0x1800111d2  mov     eax, [rdi+28h]
0x1800111d5  mov     r13, r15
0x1800111d8  sub     eax, [rdi+0Ch]
0x1800111db  lea     rcx, [rax+rax*2]
0x1800111df  mov     rax, [rdi+20h]
0x1800111e3  lea     r14, [rax+rcx*8]
0x1800111e7  test    ebx, ebx
0x1800111e9  js      loc_1800112A0
0x1800111ef  test    r13, r13
0x1800111f2  jz      loc_1800112A0
0x1800111f8  add     r14, 8
0x1800111fc  jz      loc_1800112A0
0x180011202  movzx   eax, word ptr [r14]
0x180011206  add     eax, 2
0x180011209  mov     ecx, eax; cb
0x18001120b  mov     ebx, eax
0x18001120d  call    cs:__imp_CoTaskMemAlloc
0x180011213  mov     rsi, rax
0x180011216  test    rax, rax
0x180011219  jz      short loc_180011293
0x18001121b  mov     r8d, ebx; unsigned int
0x18001121e  mov     rdx, rax; unsigned __int16 *
0x180011221  mov     rcx, r14; struct _UNICODE_STRING *
0x180011224  call    ?CopyUstrToPstr@@YAJQEAU_UNICODE_STRING@@PEAGK@Z; CopyUstrToPstr(_UNICODE_STRING * const,ushort *,ulong)
0x180011229  mov     ebx, eax
0x18001122b  test    eax, eax
0x18001122d  js      short loc_180011288
0x18001122f  mov     rcx, [rdi]
0x180011232  lea     r9, [rsp+78h+var_40]
0x180011237  mov     r8, rsi
0x18001123a  mov     rdx, r13
0x18001123d  mov     rax, [rcx+48h]
0x180011241  mov     rcx, rdi
0x180011244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011249  mov     ebx, eax
0x18001124b  test    eax, eax
0x18001124d  js      short loc_18001125A
0x18001124f  inc     dword ptr [rdi+28h]
0x180011252  mov     r12d, 1
0x180011258  jmp     short loc_180011288
0x18001125a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011261  lea     rax, WPP_GLOBAL_Control
0x180011268  cmp     rcx, rax
0x18001126b  jz      short loc_180011288
0x18001126d  test    byte ptr [rcx+1Ch], 2
0x180011271  jz      short loc_180011288
0x180011273  mov     rcx, [rcx+10h]
0x180011277  mov     edx, 1Ch
0x18001127c  mov     r9, rsi
0x18001127f  mov     [rsp+78h+var_58], ebx
0x180011283  call    WPP_SF_SD
0x180011288  mov     rcx, rsi; pv
0x18001128b  call    cs:__imp_CoTaskMemFree
0x180011291  jmp     short loc_180011298
0x180011293  mov     ebx, 8007000Eh
0x180011298  mov     rsi, [rsp+78h+arg_18]
0x1800112a0  test    rbp, rbp
0x1800112a3  jz      short loc_1800112AE
0x1800112a5  mov     rcx, rbp; pv
0x1800112a8  call    cs:__imp_CoTaskMemFree
0x1800112ae  test    r15, r15
0x1800112b1  jz      short loc_1800112BC
0x1800112b3  mov     rcx, r15; pv
0x1800112b6  call    cs:__imp_CoTaskMemFree
0x1800112bc  test    r12d, r12d
0x1800112bf  jz      short loc_1800112C7
0x1800112c1  test    ebx, ebx
0x1800112c3  js      short loc_1800112E4
0x1800112c5  jmp     short loc_1800112CC
0x1800112c7  mov     ebx, 1
0x1800112cc  mov     rax, [rsp+78h+arg_10]
0x1800112d4  mov     rcx, [rsp+78h+var_40]
0x1800112d9  mov     [rax], rcx
0x1800112dc  test    rsi, rsi
0x1800112df  jz      short loc_1800112E4
0x1800112e1  mov     [rsi], r12d
0x1800112e4  mov     eax, ebx
0x1800112e6  mov     rbx, [rsp+78h+arg_8]
0x1800112ee  add     rsp, 40h
0x1800112f2  pop     r15
0x1800112f4  pop     r14
0x1800112f6  pop     r13
0x1800112f8  pop     r12
0x1800112fa  pop     rdi
0x1800112fb  pop     rsi
0x1800112fc  pop     rbp
0x1800112fd  retn
```
