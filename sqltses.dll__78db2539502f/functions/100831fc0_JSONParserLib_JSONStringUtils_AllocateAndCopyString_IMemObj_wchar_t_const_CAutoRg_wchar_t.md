# JSONParserLib::JSONStringUtils::AllocateAndCopyString(IMemObj *,wchar_t const *,CAutoRg<wchar_t> &)

- ea: `0x100831fc0`
- end: `0x100832123`
- name: `?AllocateAndCopyString@JSONStringUtils@JSONParserLib@@SAKPEAVIMemObj@@PEB_WAEAV?$CAutoRg@_W@@@Z`
- size: `355`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x10082c180`
- `0x10082cfb0`
- `0x10082e560`

## callees

- `0x100831fc0`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10083206f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10083206f`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831ff9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008320eb`
- `sqldk!??_V@YAXPEAX@Z` at `0x100832100`
- `sqldk!??_V@YAXPEAX@Z` at `0x100831ff9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1008320eb`
- `sqldk!??_V@YAXPEAX@Z` at `0x100832100`

## string_xrefs

- `0x100832059`: `Sql\Ntdbms\storeng\jsonparser\src\JSON_StringUtils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JSONParserLib::JSONStringUtils::AllocateAndCopyString(struct IMemObj *a1, char *a2, void **a3)
{
  unsigned __int64 v6; // rdi
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  unsigned int v9; // r14d
  void *v10; // r15
  void *v11; // rbx
  __int64 v12; // rdx
  _WORD *v13; // rax
  __int16 v14; // cx
  __int16 v15; // cx

  if ( a2 )
  {
    v6 = 0;
    v7 = 0;
    if ( *(_WORD *)a2 )
    {
      while ( (unsigned __int64)++v7 <= 0x7FFFFFFE )
      {
        if ( !*(_WORD *)&a2[2 * v7] )
          goto LABEL_8;
      }
    }
    else
    {
LABEL_8:
      v6 = v7 + 1;
    }
    v8 = 4 * v6;
    if ( !is_mul_ok(2 * v6, 2u) )
      v8 = -1;
    v9 = 1;
    v10 = operator new[](v8, a1, 1, "Sql\\Ntdbms\\storeng\\jsonparser\\src\\JSON_StringUtils.cpp", 51, 6u);
    v11 = v10;
    if ( v10 )
    {
      if ( v6 - 1 > 0x7FFFFFFE )
      {
        v9 = 2;
      }
      else
      {
        v12 = 0;
        if ( v6 > 1 )
        {
          v13 = v10;
          do
          {
            v14 = *(_WORD *)((char *)v13 + a2 - (_BYTE *)v10);
            if ( !v14 )
              break;
            *v13 = v14;
            --v6;
            ++v12;
            ++v13;
          }
          while ( v6 > 1 );
        }
        *((_WORD *)v10 + v12) = 0;
        v15 = *(_WORD *)&a2[2 * v12];
        v9 = v15 != 0 ? 3 : 0;
        if ( !v15 )
        {
          v11 = 0;
          if ( *a3 != v10 )
            operator delete[](*a3);
          *a3 = v10;
        }
      }
    }
    operator delete[](v11);
    return v9;
  }
  else
  {
    if ( *a3 )
      operator delete[](*a3);
    *a3 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x100831fc0  push    rsi
0x100831fc2  push    rdi
0x100831fc3  push    r12
0x100831fc5  push    r14
0x100831fc7  push    r15
0x100831fc9  sub     rsp, 40h
0x100831fcd  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x100831fd6  mov     [rsp+68h+arg_0], rbx
0x100831fdb  mov     [rsp+68h+arg_10], rbp
0x100831fe3  mov     r12, r8
0x100831fe6  mov     rsi, rdx
0x100831fe9  mov     r10, rcx
0x100831fec  test    rdx, rdx
0x100831fef  jnz     short loc_10083200C
0x100831ff1  mov     rcx, [r8]
0x100831ff4  test    rcx, rcx
0x100831ff7  jz      short loc_100831FFF
0x100831ff9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100831fff  xor     ebp, ebp
0x100832001  mov     [r12], rbp
0x100832005  xor     eax, eax
0x100832007  jmp     loc_100832109
0x10083200c  xor     ebp, ebp
0x10083200e  mov     edi, ebp
0x100832010  mov     eax, ebp
0x100832012  cmp     [rdx], ax
0x100832015  jz      short loc_100832031
0x100832017  nop     word ptr [rax+rax]
0x10083201c  nop     dword ptr [rax+00h]
0x100832020  inc     rax
0x100832023  cmp     rax, 7FFFFFFEh
0x100832029  ja      short loc_100832035
0x10083202b  cmp     [rdx+rax*2], di
0x10083202f  jnz     short loc_100832020
0x100832031  lea     rdi, [rax+1]
0x100832035  lea     rcx, [rdi+rdi]
0x100832039  mov     eax, 2
0x10083203e  mul     rcx
0x100832041  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x100832048  cmovo   rax, rcx
0x10083204c  mov     [rsp+68h+var_40], 6
0x100832051  mov     [rsp+68h+var_48], 33h ; '3'
0x100832059  lea     r9, aSqlNtdbmsStore_2; "Sql\\Ntdbms\\storeng\\jsonparser\\src\\"...
0x100832060  mov     r14d, 1
0x100832066  mov     r8d, r14d
0x100832069  mov     rdx, r10
0x10083206c  mov     rcx, rax
0x10083206f  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100832075  mov     r15, rax
0x100832078  mov     rbx, rax
0x10083207b  mov     [rsp+68h+arg_8], rax
0x100832080  test    rax, rax
0x100832083  jz      short loc_1008320FD
0x100832085  lea     rax, [rdi-1]
0x100832089  cmp     rax, 7FFFFFFEh
0x10083208f  ja      short loc_1008320F7
0x100832091  mov     rdx, rbp
0x100832094  cmp     rdi, r14
0x100832097  jbe     short loc_1008320BF
0x100832099  mov     rax, rbx
0x10083209c  mov     r8, rsi
0x10083209f  sub     r8, rbx
0x1008320a2  movzx   ecx, word ptr [r8+rax]
0x1008320a7  test    cx, cx
0x1008320aa  jz      short loc_1008320BF
0x1008320ac  mov     [rax], cx
0x1008320af  dec     rdi
0x1008320b2  inc     rdx
0x1008320b5  add     rax, 2
0x1008320b9  cmp     rdi, 1
0x1008320bd  ja      short loc_1008320A2
0x1008320bf  mov     [r15+rdx*2], bp
0x1008320c4  movzx   ecx, word ptr [rsi+rdx*2]
0x1008320c8  movzx   eax, cx
0x1008320cb  neg     ax
0x1008320ce  sbb     r14d, r14d
0x1008320d1  and     r14d, 3
0x1008320d5  test    cx, cx
0x1008320d8  jnz     short loc_1008320FD
0x1008320da  mov     rbx, rbp
0x1008320dd  mov     [rsp+68h+arg_8], rbx
0x1008320e2  mov     rcx, [r12]
0x1008320e6  cmp     rcx, r15
0x1008320e9  jz      short loc_1008320F1
0x1008320eb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1008320f1  mov     [r12], r15
0x1008320f5  jmp     short loc_1008320FD
0x1008320f7  mov     r14d, 2
0x1008320fd  mov     rcx, rbx
0x100832100  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x100832106  mov     eax, r14d
0x100832109  mov     rbx, [rsp+68h+arg_0]
0x10083210e  mov     rbp, [rsp+68h+arg_10]
0x100832116  add     rsp, 40h
0x10083211a  pop     r15
0x10083211c  pop     r14
0x10083211e  pop     r12
0x100832120  pop     rdi
0x100832121  pop     rsi
0x100832122  retn
```
