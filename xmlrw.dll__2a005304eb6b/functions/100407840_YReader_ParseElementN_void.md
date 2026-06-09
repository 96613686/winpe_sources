# YReader::ParseElementN(void)

- ea: `0x100407840`
- end: `0x1004079c8`
- name: `?ParseElementN@YReader@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x100401780`
- `0x1004019c0`
- `0x100407840`
- `0x10040ae50`
- `0x10040c8e0`
- `0x1004157a0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseElementN(YReader *this)
{
  char *v1; // rdi
  unsigned int v3; // ecx
  __int64 v4; // rax
  __int64 v5; // rcx
  void (__fastcall *v6)(char *); // rax
  __int64 v7; // rcx
  __int64 v8; // rax

  v1 = (char *)this + 1864;
  v3 = *((_DWORD *)this + 472);
  if ( *((_DWORD *)v1 + 7) == v3 )
  {
    _stack<YReader::Element,16>::grow((__int64)v1, 0);
    v3 = *((_DWORD *)v1 + 6);
  }
  *((_DWORD *)v1 + 6) = v3 + 1;
  *((_QWORD *)this + 349) = *((_QWORD *)v1 + 2) + 56LL * v3;
  YReader::GetTokenQName(this, (YReader *)((char *)this + 1568), (YReader *)((char *)this + 1584));
  ++*((_DWORD *)this + 132);
  v4 = *((_QWORD *)this + 55);
  *((_QWORD *)this + 350) = 0;
  v5 = *(_QWORD *)(v4 + 16);
  v6 = (void (__fastcall *)(char *))*((_QWORD *)this + 194);
  *((_QWORD *)this + 231) = v5;
  v6((char *)this + *((int *)this + 390));
  *((_QWORD *)this + 230) = *(_QWORD *)(*((_QWORD *)this + 55) + 16LL);
  YReader::ProcessAttributesN(this);
  v7 = *((unsigned int *)this + 398);
  if ( (_DWORD)v7 )
  {
    *((_QWORD *)this + 202) = *((_QWORD *)this + 196) + 2LL + 2 * v7;
    *((_DWORD *)this + 406) = *((_DWORD *)this + 394) - v7 - 1;
  }
  else
  {
    *((_OWORD *)this + 101) = *((_OWORD *)this + 98);
  }
  if ( !NamespaceSupport::ProcessPrefix(
          (YReader *)((char *)this + 512),
          (YReader *)((char *)this + 1584),
          (YReader *)((char *)this + 1600)) )
  {
    MXRRaiseException(-1072894363);
    JUMPOUT(0x1004079C7LL);
  }
  *(_OWORD *)*((_QWORD *)this + 349) = *((_OWORD *)this + 98);
  *(_OWORD *)(*((_QWORD *)this + 349) + 16LL) = *((_OWORD *)this + 100);
  *(_OWORD *)(*((_QWORD *)this + 349) + 32LL) = *((_OWORD *)this + 101);
  v8 = *((_QWORD *)this + 349);
  *((_BYTE *)this + 1784) = 1;
  *(_DWORD *)(v8 + 48) = 0;
}

```

## disassembly

```asm
0x100407840  mov     [rsp+arg_0], rbx
0x100407845  mov     [rsp+arg_8], rbp
0x10040784a  mov     [rsp+arg_10], rsi
0x10040784f  mov     [rsp+arg_18], rdi
0x100407854  push    r14
0x100407856  sub     rsp, 20h
0x10040785a  lea     rdi, [rcx+748h]
0x100407861  mov     rbx, rcx
0x100407864  mov     ecx, [rdi+18h]
0x100407867  cmp     [rdi+1Ch], ecx
0x10040786a  jnz     short loc_100407879
0x10040786c  xor     edx, edx
0x10040786e  mov     rcx, rdi
0x100407871  call    ?grow@?$_stack@UElement@YReader@@$0BA@@@AEAAXI@Z; _stack<YReader::Element,16>::grow(uint)
0x100407876  mov     ecx, [rdi+18h]
0x100407879  lea     eax, [rcx+1]
0x10040787c  mov     [rdi+18h], eax
0x10040787f  lea     r8, [rbx+630h]; struct StringPtr *
0x100407886  mov     eax, ecx
0x100407888  lea     rdx, [rbx+620h]; struct StringPtr *
0x10040788f  imul    rcx, rax, 38h ; '8'
0x100407893  add     rcx, [rdi+10h]
0x100407897  mov     [rbx+0AE8h], rcx
0x10040789e  mov     rcx, rbx; this
0x1004078a1  call    ?GetTokenQName@YReader@@AEAAXPEAUStringPtr@@0@Z; YReader::GetTokenQName(StringPtr *,StringPtr *)
0x1004078a6  inc     dword ptr [rbx+210h]
0x1004078ac  mov     rax, [rbx+1B8h]
0x1004078b3  mov     qword ptr [rbx+0AF0h], 0
0x1004078be  mov     rcx, [rax+10h]
0x1004078c2  mov     rax, [rbx+610h]
0x1004078c9  mov     [rbx+738h], rcx
0x1004078d0  movsxd  rcx, dword ptr [rbx+618h]
0x1004078d7  add     rcx, rbx
0x1004078da  call    cs:__guard_dispatch_icall_fptr
0x1004078e0  mov     rax, [rbx+1B8h]
0x1004078e7  mov     rcx, [rax+10h]
0x1004078eb  mov     [rbx+730h], rcx
0x1004078f2  mov     rcx, rbx; this
0x1004078f5  call    ?ProcessAttributesN@YReader@@AEAAXXZ; YReader::ProcessAttributesN(void)
0x1004078fa  mov     ecx, [rbx+638h]
0x100407900  test    ecx, ecx
0x100407902  jnz     short loc_100407914
0x100407904  movups  xmm0, xmmword ptr [rbx+620h]
0x10040790b  movups  xmmword ptr [rbx+650h], xmm0
0x100407912  jmp     short loc_10040793A
0x100407914  mov     rax, [rbx+620h]
0x10040791b  add     rax, 2
0x10040791f  lea     r8, [rax+rcx*2]
0x100407923  mov     [rbx+650h], r8
0x10040792a  mov     eax, [rbx+628h]
0x100407930  sub     eax, ecx
0x100407932  dec     eax
0x100407934  mov     [rbx+658h], eax
0x10040793a  lea     r8, [rbx+640h]; struct StringPtr *
0x100407941  lea     rdx, [rbx+630h]; struct StringPtr *
0x100407948  lea     rcx, [rbx+200h]; this
0x10040794f  call    ?ProcessPrefix@NamespaceSupport@@QEAA_NPEAUStringPtr@@0@Z; NamespaceSupport::ProcessPrefix(StringPtr *,StringPtr *)
0x100407954  test    al, al
0x100407956  jz      short loc_1004079BD
0x100407958  mov     rax, [rbx+0AE8h]
0x10040795f  movups  xmm0, xmmword ptr [rbx+620h]
0x100407966  mov     rbp, [rsp+28h+arg_8]
0x10040796b  mov     rsi, [rsp+28h+arg_10]
0x100407970  mov     rdi, [rsp+28h+arg_18]
0x100407975  movups  xmmword ptr [rax], xmm0
0x100407978  mov     rax, [rbx+0AE8h]
0x10040797f  movups  xmm0, xmmword ptr [rbx+640h]
0x100407986  movups  xmmword ptr [rax+10h], xmm0
0x10040798a  mov     rax, [rbx+0AE8h]
0x100407991  movups  xmm0, xmmword ptr [rbx+650h]
0x100407998  movups  xmmword ptr [rax+20h], xmm0
0x10040799c  mov     rax, [rbx+0AE8h]
0x1004079a3  mov     byte ptr [rbx+6F8h], 1
0x1004079aa  mov     rbx, [rsp+28h+arg_0]
0x1004079af  mov     dword ptr [rax+30h], 0
0x1004079b6  add     rsp, 20h
0x1004079ba  pop     r14
0x1004079bc  retn
0x1004079bd  mov     ecx, 0C00CEE65h; int
0x1004079c2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
