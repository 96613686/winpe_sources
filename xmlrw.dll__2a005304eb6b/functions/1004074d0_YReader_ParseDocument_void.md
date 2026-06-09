# YReader::ParseDocument(void)

- ea: `0x1004074d0`
- end: `0x1004075d3`
- name: `?ParseDocument@YReader@@AEAAXXZ`
- size: `259`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x100401780`
- `0x1004074d0`
- `0x1004098d0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseDocument(void (__fastcall **this)(char *))
{
  __int128 v2; // xmm0
  char v3; // cl
  void (__fastcall **v4)(YReader *); // rax
  __int128 v5; // [rsp+20h] [rbp-28h] BYREF
  void (__fastcall *v6)(YReader *); // [rsp+30h] [rbp-18h] BYREF
  int v7; // [rsp+38h] [rbp-10h]

  this[27]((char *)this + 40);
  if ( *((_DWORD *)this + 28) == 1 )
  {
    YReader::ParseXmlDecl((YReader *)this);
  }
  else if ( *((_DWORD *)this + 28) == 59 )
  {
    if ( !*((_BYTE *)this + 1790) )
    {
      MXRRaiseException(-1072894406);
      JUMPOUT(0x1004075D2LL);
    }
    *((_DWORD *)this + 445) = 1;
    DWORD2(v5) = 0;
    *(_QWORD *)&v5 = YReader::ParseDocumentEnd;
    v2 = v5;
    *((_DWORD *)this + 444) = 0;
    *((_OWORD *)this + 94) = v2;
    return;
  }
  this[230] = (void (__fastcall *)(char *))*((_QWORD *)this[55] + 2);
  v3 = *((_BYTE *)this + 1790);
  if ( v3 )
  {
    v6 = YReader::ParseFragmentProlog;
    v7 = 0;
  }
  else
  {
    *(_QWORD *)&v5 = YReader::ParseProlog;
    DWORD2(v5) = 0;
  }
  v4 = (void (__fastcall **)(YReader *))&v5;
  if ( v3 )
    v4 = &v6;
  *((_OWORD *)this + 94) = *(_OWORD *)v4;
  this[188]((char *)this + *((int *)this + 378));
}

```

## disassembly

```asm
0x1004074d0  mov     [rsp+arg_0], rbx
0x1004074d5  push    rdi
0x1004074d6  sub     rsp, 40h
0x1004074da  mov     rdi, rcx
0x1004074dd  add     rcx, 28h ; '('
0x1004074e1  mov     rax, [rdi+0D8h]
0x1004074e8  call    cs:__guard_dispatch_icall_fptr
0x1004074ee  mov     ecx, [rdi+70h]
0x1004074f1  sub     ecx, 1
0x1004074f4  jz      short loc_100407541
0x1004074f6  cmp     ecx, 3Ah ; ':'
0x1004074f9  jnz     short loc_100407549
0x1004074fb  cmp     byte ptr [rdi+6FEh], 0
0x100407502  jz      loc_1004075C8
0x100407508  xor     eax, eax
0x10040750a  mov     dword ptr [rdi+6F4h], 1
0x100407514  lea     rcx, ?ParseDocumentEnd@YReader@@AEAAXXZ; YReader::ParseDocumentEnd(void)
0x10040751b  mov     dword ptr [rsp+48h+var_28+8], eax
0x10040751f  mov     qword ptr [rsp+48h+var_28], rcx
0x100407524  movups  xmm0, [rsp+48h+var_28]
0x100407529  mov     [rdi+6F0h], eax
0x10040752f  movups  xmmword ptr [rdi+5E0h], xmm0
0x100407536  mov     rbx, [rsp+48h+arg_0]
0x10040753b  add     rsp, 40h
0x10040753f  pop     rdi
0x100407540  retn
0x100407541  mov     rcx, rdi; this
0x100407544  call    ?ParseXmlDecl@YReader@@AEAAXXZ; YReader::ParseXmlDecl(void)
0x100407549  mov     rax, [rdi+1B8h]
0x100407550  mov     rcx, [rax+10h]
0x100407554  mov     [rdi+730h], rcx
0x10040755b  movzx   ecx, byte ptr [rdi+6FEh]
0x100407562  test    cl, cl
0x100407564  jz      short loc_10040757A
0x100407566  lea     rax, ?ParseFragmentProlog@YReader@@AEAAXXZ; YReader::ParseFragmentProlog(void)
0x10040756d  mov     [rsp+48h+var_18], rax
0x100407572  xor     eax, eax
0x100407574  mov     [rsp+48h+var_10], eax
0x100407578  jmp     short loc_10040758C
0x10040757a  lea     rax, ?ParseProlog@YReader@@AEAAXXZ; YReader::ParseProlog(void)
0x100407581  mov     qword ptr [rsp+48h+var_28], rax
0x100407586  xor     eax, eax
0x100407588  mov     dword ptr [rsp+48h+var_28+8], eax
0x10040758c  test    cl, cl
0x10040758e  lea     rdx, [rsp+48h+var_18]
0x100407593  lea     rax, [rsp+48h+var_28]
0x100407598  cmovnz  rax, rdx
0x10040759c  movups  xmm0, xmmword ptr [rax]
0x10040759f  movups  xmmword ptr [rdi+5E0h], xmm0
0x1004075a6  movsxd  rcx, dword ptr [rdi+5E8h]
0x1004075ad  mov     rax, [rdi+5E0h]
0x1004075b4  add     rcx, rdi
0x1004075b7  mov     rbx, [rsp+48h+arg_0]
0x1004075bc  add     rsp, 40h
0x1004075c0  pop     rdi
0x1004075c1  jmp     cs:__guard_dispatch_icall_fptr
0x1004075c8  mov     ecx, 0C00CEE3Ah; int
0x1004075cd  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
