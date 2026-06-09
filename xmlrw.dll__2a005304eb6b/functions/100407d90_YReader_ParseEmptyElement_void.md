# YReader::ParseEmptyElement(void)

- ea: `0x100407d90`
- end: `0x100407eb9`
- name: `?ParseEmptyElement@YReader@@AEAAXXZ`
- size: `297`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x100407d20`
- `0x100407d40`

## callees

- `0x100401780`
- `0x100407d90`
- `0x100415ce0`
- `0x100415fd0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseEmptyElement(YReader *this)
{
  char *v1; // rbx
  __int64 v3; // r10
  unsigned int i; // eax
  int v5; // ecx
  __int64 v6; // rax
  __int128 v7; // [rsp+20h] [rbp-18h]
  int v8; // [rsp+40h] [rbp+8h] BYREF

  v1 = (char *)this + 512;
  v3 = *((_QWORD *)this + 69) + 40LL * (unsigned int)(*((_DWORD *)this + 140) - 1);
  for ( i = *((_DWORD *)this + 132); *(_DWORD *)(v3 + 32) == i; i = *((_DWORD *)v1 + 4) )
  {
    if ( v1[736] )
      _dict<unsigned int,0>::replace((__int64)(v1 + 696), (const void **)v3, *(_DWORD *)(v3 + 36), &v8);
    NamespaceSupport::PopPrefix((NamespaceSupport *)v1);
    v3 = *((_QWORD *)v1 + 5) + 40LL * (unsigned int)(*((_DWORD *)v1 + 12) - 1);
  }
  if ( i <= 1 )
  {
    MXRRaiseException(-2147418113);
    JUMPOUT(0x100407EB8LL);
  }
  *((_DWORD *)v1 + 4) = i - 1;
  *((_QWORD *)this + 230) = **((_QWORD **)this + 349);
  v5 = *((_DWORD *)this + 472) - 1;
  *((_BYTE *)this + 1784) = 1;
  *((_DWORD *)this + 472) = v5;
  if ( v5 )
  {
    *(_QWORD *)&v7 = YReader::ParseContent;
    DWORD2(v7) = 0;
    *((_OWORD *)this + 94) = v7;
    v6 = *((_QWORD *)this + 235) + 56LL * (unsigned int)(v5 - 1);
  }
  else
  {
    *(_QWORD *)&v7 = YReader::ParseEpilog;
    v6 = 0;
    DWORD2(v7) = 0;
    *((_OWORD *)this + 94) = v7;
  }
  *((_QWORD *)this + 349) = v6;
  (*((void (__fastcall **)(char *))this + 188))((char *)this + *((int *)this + 378));
}

```

## disassembly

```asm
0x100407d90  mov     [rsp+arg_8], rbx
0x100407d95  push    rdi
0x100407d96  sub     rsp, 30h
0x100407d9a  lea     rbx, [rcx+200h]
0x100407da1  mov     rdi, rcx
0x100407da4  mov     eax, [rbx+30h]
0x100407da7  dec     eax
0x100407da9  lea     rdx, [rax+rax*4]
0x100407dad  mov     rax, [rbx+28h]
0x100407db1  lea     r10, [rax+rdx*8]
0x100407db5  mov     eax, [rbx+10h]
0x100407db8  cmp     [r10+20h], eax
0x100407dbc  jnz     short loc_100407E03
0x100407dbe  xchg    ax, ax
0x100407dc0  cmp     byte ptr [rbx+2E0h], 0
0x100407dc7  jz      short loc_100407DE1
0x100407dc9  mov     r8d, [r10+24h]
0x100407dcd  lea     rcx, [rbx+2B8h]
0x100407dd4  lea     r9, [rsp+38h+arg_0]
0x100407dd9  mov     rdx, r10
0x100407ddc  call    ?replace@?$_dict@I$0A@@@QEAAXPEAUStringPtr@@IPEAI@Z; _dict<uint,0>::replace(StringPtr *,uint,uint *)
0x100407de1  mov     rcx, rbx; this
0x100407de4  call    ?PopPrefix@NamespaceSupport@@AEAAXXZ; NamespaceSupport::PopPrefix(void)
0x100407de9  mov     eax, [rbx+30h]
0x100407dec  dec     eax
0x100407dee  lea     rcx, [rax+rax*4]
0x100407df2  mov     rax, [rbx+28h]
0x100407df6  lea     r10, [rax+rcx*8]
0x100407dfa  mov     eax, [rbx+10h]
0x100407dfd  cmp     [r10+20h], eax
0x100407e01  jz      short loc_100407DC0
0x100407e03  cmp     eax, 1
0x100407e06  jbe     loc_100407EAE
0x100407e0c  dec     eax
0x100407e0e  mov     [rbx+10h], eax
0x100407e11  mov     rax, [rdi+0AE8h]
0x100407e18  mov     rcx, [rax]
0x100407e1b  mov     [rdi+730h], rcx
0x100407e22  mov     ecx, [rdi+760h]
0x100407e28  sub     ecx, 1
0x100407e2b  mov     byte ptr [rdi+6F8h], 1
0x100407e32  mov     [rdi+760h], ecx
0x100407e38  jz      short loc_100407E67
0x100407e3a  lea     rax, ?ParseContent@YReader@@AEAAXXZ; YReader::ParseContent(void)
0x100407e41  dec     ecx
0x100407e43  mov     qword ptr [rsp+38h+var_18], rax
0x100407e48  xor     eax, eax
0x100407e4a  mov     dword ptr [rsp+38h+var_18+8], eax
0x100407e4e  movups  xmm0, [rsp+38h+var_18]
0x100407e53  imul    rax, rcx, 38h ; '8'
0x100407e57  movups  xmmword ptr [rdi+5E0h], xmm0
0x100407e5e  add     rax, [rdi+758h]
0x100407e65  jmp     short loc_100407E85
0x100407e67  lea     rax, ?ParseEpilog@YReader@@AEAAXXZ; YReader::ParseEpilog(void)
0x100407e6e  mov     qword ptr [rsp+38h+var_18], rax
0x100407e73  xor     eax, eax
0x100407e75  mov     dword ptr [rsp+38h+var_18+8], eax
0x100407e79  movups  xmm0, [rsp+38h+var_18]
0x100407e7e  movups  xmmword ptr [rdi+5E0h], xmm0
0x100407e85  mov     [rdi+0AE8h], rax
0x100407e8c  movsxd  rcx, dword ptr [rdi+5E8h]
0x100407e93  mov     rax, [rdi+5E0h]
0x100407e9a  add     rcx, rdi
0x100407e9d  mov     rbx, [rsp+38h+arg_8]
0x100407ea2  add     rsp, 30h
0x100407ea6  pop     rdi
0x100407ea7  jmp     cs:__guard_dispatch_icall_fptr
0x100407eae  mov     ecx, 8000FFFFh; int
0x100407eb3  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
