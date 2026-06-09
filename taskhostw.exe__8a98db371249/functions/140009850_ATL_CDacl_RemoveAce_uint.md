# ATL::CDacl::RemoveAce(uint)

- ea: `0x140009850`
- end: `0x1400098c8`
- name: `?RemoveAce@CDacl@ATL@@UEAAXI@Z`
- size: `120`
- prototype: `void __fastcall(ATL::CDacl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140003130`
- `0x140006500`
- `0x1400072bc`
- `0x140009850`

## import_xrefs

- `msvcrt!memmove_s` at `0x1400098a3`
- `msvcrt!memmove_s` at `0x1400098a3`

## pseudocode

```c
void __fastcall ATL::CDacl::RemoveAce(ATL::CDacl *this, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rbp
  errno_t v7; // eax

  v2 = a2;
  v4 = a2 + 1LL;
  if ( v4 < a2 || a2 == -1 || (v5 = *((_QWORD *)this + 4), v4 > v5) )
    ATL::PrivateAtlThrow(-2147024809);
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
    *((_QWORD *)this + 3) + 8LL * a2,
    1u);
  v6 = v5 - v4;
  if ( v6 )
  {
    v7 = memmove_s(
           (void *const)(*((_QWORD *)this + 3) + 8 * v2),
           8 * v6,
           (const void *const)(*((_QWORD *)this + 3) + 8 * v4),
           8 * v6);
    ATL::AtlCrtErrorCheck(v7);
  }
  --*((_QWORD *)this + 4);
}

```

## disassembly

```asm
0x140009850  push    rbx
0x140009852  push    rbp
0x140009853  push    rsi
0x140009854  push    rdi
0x140009855  sub     rsp, 28h
0x140009859  mov     esi, edx
0x14000985b  mov     rbx, rcx
0x14000985e  lea     rdi, [rsi+1]
0x140009862  cmp     rdi, rsi
0x140009865  jb      short loc_1400098BD
0x140009867  mov     edx, 1
0x14000986c  cmp     rdi, rdx
0x14000986f  jb      short loc_1400098BD
0x140009871  mov     rbp, [rcx+20h]
0x140009875  cmp     rdi, rbp
0x140009878  ja      short loc_1400098BD
0x14000987a  mov     rax, [rcx+18h]
0x14000987e  lea     rcx, [rax+rsi*8]
0x140009882  call    ?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)
0x140009887  sub     rbp, rdi
0x14000988a  jz      short loc_1400098B0
0x14000988c  mov     rax, [rbx+18h]
0x140009890  lea     rdx, ds:0[rbp*8]; DestinationSize
0x140009898  mov     r9, rdx; SourceSize
0x14000989b  lea     r8, [rax+rdi*8]; Source
0x14000989f  lea     rcx, [rax+rsi*8]; Destination
0x1400098a3  call    cs:__imp_memmove_s
0x1400098a9  mov     ecx, eax; int
0x1400098ab  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400098b0  dec     qword ptr [rbx+20h]
0x1400098b4  add     rsp, 28h
0x1400098b8  pop     rdi
0x1400098b9  pop     rsi
0x1400098ba  pop     rbp
0x1400098bb  pop     rbx
0x1400098bc  retn
0x1400098bd  mov     ecx, 80070057h; int
0x1400098c2  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```
