# DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)

- ea: `0x180017b20`
- end: `0x180017c49`
- name: `?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z`
- size: `297`
- prototype: `void __fastcall(struct DirectUI::Element *, void (*)(struct IUnknown *, __int64), __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a9f0`
- `0x180017b20`
- `0x180017c80`
- `0x180017cf0`
- `0x180017d30`
- `0x180017d60`
- `0x180017d90`
- `0x180017de0`
- `0x180017e70`
- `0x180017ea0`

## callees

- `0x180017b20`
- `0x18001e010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180017bce`
- `KERNEL32!CompareStringOrdinal` at `0x180017bce`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017c32`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180017c32`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180017b4e`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180017b4e`

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
0x180017b20  test    rcx, rcx
0x180017b23  jz      locret_180017C48
0x180017b29  mov     rax, rsp
0x180017b2c  push    rbx
0x180017b2d  push    rbp
0x180017b2e  push    rsi
0x180017b2f  push    rdi
0x180017b30  push    r12
0x180017b32  push    r13
0x180017b34  push    r14
0x180017b36  push    r15
0x180017b38  sub     rsp, 38h
0x180017b3c  mov     r13, rdx
0x180017b3f  mov     qword ptr [rax+8], 0
0x180017b47  lea     rdx, [rax+8]
0x180017b4b  mov     r12, r8
0x180017b4e  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180017b54  mov     rsi, rax
0x180017b57  test    rax, rax
0x180017b5a  jz      loc_180017C38
0x180017b60  mov     ecx, [rax]
0x180017b62  test    ecx, 0FFFFFFFh
0x180017b68  jbe     loc_180017C2A
0x180017b6e  xor     ebp, ebp
0x180017b70  bt      ecx, 1Ch
0x180017b74  jnb     short loc_180017B7C
0x180017b76  mov     r14, [rsi+8]
0x180017b7a  jmp     short loc_180017B80
0x180017b7c  lea     r14, [rsi+8]
0x180017b80  mov     r14, [r14+rbp*8]
0x180017b84  mov     rcx, r14
0x180017b87  mov     rax, [r14]
0x180017b8a  mov     rax, [rax+118h]
0x180017b91  jmp     short loc_180017BE3
0x180017b93  mov     rcx, cs:?Class@CElementWithIUnknown@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CElementWithIUnknown::Class
0x180017b9a  mov     rdx, [rcx]
0x180017b9d  mov     rax, [rdx+40h]
0x180017ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ba6  mov     rcx, [rdi]
0x180017ba9  mov     rbx, rax
0x180017bac  mov     rax, [rcx+40h]
0x180017bb0  mov     rcx, rdi
0x180017bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb8  or      ecx, 0FFFFFFFFh
0x180017bbb  mov     [rsp+78h+bIgnoreCase], 0; bIgnoreCase
0x180017bc3  mov     r9d, ecx; cchCount2
0x180017bc6  mov     edx, ecx; cchCount1
0x180017bc8  mov     rcx, rax; lpString1
0x180017bcb  mov     r8, rbx; lpString2
0x180017bce  call    cs:__imp_CompareStringOrdinal
0x180017bd4  cmp     eax, 2
0x180017bd7  jz      short loc_180017BF2
0x180017bd9  mov     rax, [rdi]
0x180017bdc  mov     rcx, rdi
0x180017bdf  mov     rax, [rax+38h]
0x180017be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017be8  mov     rdi, rax
0x180017beb  test    rax, rax
0x180017bee  jnz     short loc_180017B93
0x180017bf0  jmp     short loc_180017C09
0x180017bf2  lea     rcx, [r14+0C8h]
0x180017bf9  test    rcx, rcx
0x180017bfc  jz      short loc_180017C09
0x180017bfe  mov     rdx, r12
0x180017c01  mov     rax, r13
0x180017c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c09  mov     r8, r12; __int64
0x180017c0c  mov     rdx, r13; void (*)(struct IUnknown *, __int64)
0x180017c0f  mov     rcx, r14; struct DirectUI::Element *
0x180017c12  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x180017c17  mov     ecx, [rsi]
0x180017c19  inc     ebp
0x180017c1b  mov     eax, ecx
0x180017c1d  and     eax, 0FFFFFFFh
0x180017c22  cmp     ebp, eax
0x180017c24  jb      loc_180017B70
0x180017c2a  mov     rcx, [rsp+78h+arg_0]
0x180017c32  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180017c38  add     rsp, 38h
0x180017c3c  pop     r15
0x180017c3e  pop     r14
0x180017c40  pop     r13
0x180017c42  pop     r12
0x180017c44  pop     rdi
0x180017c45  pop     rsi
0x180017c46  pop     rbp
0x180017c47  pop     rbx
0x180017c48  retn
```
