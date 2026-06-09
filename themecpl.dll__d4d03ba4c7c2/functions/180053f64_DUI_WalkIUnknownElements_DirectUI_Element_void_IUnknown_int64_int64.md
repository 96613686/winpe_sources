# DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)

- ea: `0x180053f64`
- end: `0x1800540a0`
- name: `?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z`
- size: `316`
- prototype: `void __fastcall(struct DirectUI::Element *, void (*)(struct IUnknown *, __int64), __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ddb0`
- `0x180035ba4`
- `0x18003bacc`
- `0x180053f64`
- `0x180054190`
- `0x180054210`
- `0x180054250`
- `0x180054290`
- `0x1800542d0`
- `0x180054330`
- `0x1800543d0`
- `0x180054410`

## callees

- `0x180053f64`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054018`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180054018`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180053f92`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180053f92`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180054082`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180054082`

## pseudocode

```c
void __fastcall DUI_WalkIUnknownElements(
        struct DirectUI::Element *a1,
        void (__fastcall *a2)(char *, __int64),
        __int64 a3)
{
  _DWORD *Children; // rax
  _DWORD *v6; // rsi
  int v7; // ecx
  __int64 v8; // rbp
  _DWORD *v9; // r14
  struct DirectUI::Element *v10; // r14
  __int64 i; // rax
  const WCHAR *v12; // rbx
  const WCHAR *v13; // rax
  __int64 v14; // rdi
  DirectUI::Value *v15; // [rsp+80h] [rbp+8h] BYREF

  if ( a1 )
  {
    v15 = 0;
    Children = (_DWORD *)DirectUI::Element::GetChildren(a1, &v15);
    v6 = Children;
    if ( Children )
    {
      v7 = *Children;
      if ( (*Children & 0xFFFFFFF) != 0 )
      {
        v8 = 0;
        do
        {
          if ( (v7 & 0x10000000) != 0 )
            v9 = (_DWORD *)*((_QWORD *)v6 + 1);
          else
            v9 = v6 + 2;
          v10 = *(struct DirectUI::Element **)&v9[2 * v8];
          for ( i = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v10 + 280LL))(v10);
                ;
                i = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14) )
          {
            v14 = i;
            if ( !i )
              break;
            v12 = (const WCHAR *)(*(__int64 (__fastcall **)(struct DirectUI::IClassInfo *))(*(_QWORD *)CElementWithIUnknown::Class
                                                                                          + 64LL))(CElementWithIUnknown::Class);
            v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 64LL))(v14);
            if ( CompareStringOrdinal(v13, -1, v12, -1, 0) == 2 )
            {
              if ( v10 != (struct DirectUI::Element *)-200LL )
                a2((char *)v10 + 200, a3);
              break;
            }
          }
          DUI_WalkIUnknownElements(v10, (void (*)(struct IUnknown *, __int64))a2, a3);
          v7 = *v6;
          v8 = (unsigned int)(v8 + 1);
        }
        while ( (unsigned int)v8 < (*v6 & 0xFFFFFFFu) );
      }
      DirectUI::Value::Release(v15);
    }
  }
}

```

## disassembly

```asm
0x180053f64  test    rcx, rcx
0x180053f67  jz      locret_18005409E
0x180053f6d  mov     rax, rsp
0x180053f70  push    rbx
0x180053f71  push    rbp
0x180053f72  push    rsi
0x180053f73  push    rdi
0x180053f74  push    r12
0x180053f76  push    r13
0x180053f78  push    r14
0x180053f7a  push    r15
0x180053f7c  sub     rsp, 38h
0x180053f80  mov     r13, rdx
0x180053f83  mov     qword ptr [rax+8], 0
0x180053f8b  lea     rdx, [rax+8]
0x180053f8f  mov     r12, r8
0x180053f92  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180053f99  nop     dword ptr [rax+rax+00h]
0x180053f9e  mov     rsi, rax
0x180053fa1  test    rax, rax
0x180053fa4  jz      loc_18005408E
0x180053faa  mov     ecx, [rax]
0x180053fac  test    ecx, 0FFFFFFFh
0x180053fb2  jbe     loc_18005407A
0x180053fb8  xor     ebp, ebp
0x180053fba  bt      ecx, 1Ch
0x180053fbe  jnb     short loc_180053FC6
0x180053fc0  mov     r14, [rsi+8]
0x180053fc4  jmp     short loc_180053FCA
0x180053fc6  lea     r14, [rsi+8]
0x180053fca  mov     r14, [r14+rbp*8]
0x180053fce  mov     rcx, r14
0x180053fd1  mov     rax, [r14]
0x180053fd4  mov     rax, [rax+118h]
0x180053fdb  jmp     short loc_180054033
0x180053fdd  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180053fe4  mov     rdx, [rcx]
0x180053fe7  mov     rax, [rdx+40h]
0x180053feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053ff0  mov     rcx, [rdi]
0x180053ff3  mov     rbx, rax
0x180053ff6  mov     rax, [rcx+40h]
0x180053ffa  mov     rcx, rdi
0x180053ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054002  or      ecx, 0FFFFFFFFh
0x180054005  mov     [rsp+78h+bIgnoreCase], 0; bIgnoreCase
0x18005400d  mov     r9d, ecx; cchCount2
0x180054010  mov     edx, ecx; cchCount1
0x180054012  mov     rcx, rax; lpString1
0x180054015  mov     r8, rbx; lpString2
0x180054018  call    cs:__imp_CompareStringOrdinal
0x18005401f  nop     dword ptr [rax+rax+00h]
0x180054024  cmp     eax, 2
0x180054027  jz      short loc_180054042
0x180054029  mov     rax, [rdi]
0x18005402c  mov     rcx, rdi
0x18005402f  mov     rax, [rax+38h]
0x180054033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054038  mov     rdi, rax
0x18005403b  test    rax, rax
0x18005403e  jnz     short loc_180053FDD
0x180054040  jmp     short loc_180054059
0x180054042  lea     rcx, [r14+0C8h]
0x180054049  test    rcx, rcx
0x18005404c  jz      short loc_180054059
0x18005404e  mov     rdx, r12
0x180054051  mov     rax, r13
0x180054054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054059  mov     r8, r12; __int64
0x18005405c  mov     rdx, r13; void (*)(struct IUnknown *, __int64)
0x18005405f  mov     rcx, r14; struct DirectUI::Element *
0x180054062  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x180054067  mov     ecx, [rsi]
0x180054069  inc     ebp
0x18005406b  mov     eax, ecx
0x18005406d  and     eax, 0FFFFFFFh
0x180054072  cmp     ebp, eax
0x180054074  jb      loc_180053FBA
0x18005407a  mov     rcx, [rsp+78h+arg_0]
0x180054082  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180054089  nop     dword ptr [rax+rax+00h]
0x18005408e  add     rsp, 38h
0x180054092  pop     r15
0x180054094  pop     r14
0x180054096  pop     r13
0x180054098  pop     r12
0x18005409a  pop     rdi
0x18005409b  pop     rsi
0x18005409c  pop     rbp
0x18005409d  pop     rbx
0x18005409e  retn
```
