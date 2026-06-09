# CWdsMetadata::AppendEntry(ushort const *)

- ea: `0x18000ba74`
- end: `0x18000bb51`
- name: `?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z`
- size: `221`
- prototype: `__int64 __fastcall(CWdsMetadata *this, const unsigned __int16 *)`
- caller_count: `14`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000b834`
- `0x18000b92c`
- `0x18000bb58`
- `0x18000bd00`
- `0x18000be10`
- `0x18000bf44`
- `0x18000c03c`
- `0x18000c158`
- `0x18000c2d0`
- `0x18000c774`
- `0x18000dde4`
- `0x18000efb0`
- `0x18000f060`
- `0x1800115e4`

## callees

- `0x180009838`
- `0x18000a15c`
- `0x18000a380`
- `0x18000a970`
- `0x18000ba74`
- `0x180014d58`
- `0x1800150b8`
- `0x18001577c`

## pseudocode

```c
__int64 __fastcall CWdsMetadata::AppendEntry(CWdsMetadata *this, const unsigned __int16 *a2)
{
  _DWORD *v4; // rax
  unsigned __int64 v5; // rbx
  unsigned int v6; // edi
  const char *v7; // rdx
  const char *v8; // rdx

  v4 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = (unsigned __int64)v4;
  if ( v4 )
  {
    v4[10] = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 7) = 0;
    *(_QWORD *)v4 = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    v4[8] = 0;
    v4[9] = 0;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    v6 = CWdsMetadataEntry::Initialize((CWdsMetadataEntry *)v5, a2);
    if ( !ElValidateWin32(v6, v7, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x1077u) )
    {
      v6 = CWdsMetadata::AddEntry(this, (struct CWdsMetadataEntry *)v5);
      v5 &= -(__int64)(ElValidateWin32(v6, v8, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x107Au) != 0);
    }
    if ( v5 )
    {
      CWdsMetadataEntry::Shutdown((CWdsMetadataEntry *)v5);
      CWdsMetadataValue::Shutdown((CWdsMetadataValue *)(v5 + 40));
      operator delete((void *)v5);
    }
  }
  else
  {
    return 8;
  }
  return v6;
}

```

## disassembly

```asm
0x18000ba74  mov     [rsp+arg_0], rbx
0x18000ba79  mov     [rsp+arg_8], rsi
0x18000ba7e  push    rdi
0x18000ba7f  sub     rsp, 20h
0x18000ba83  mov     rdi, rdx
0x18000ba86  mov     rsi, rcx
0x18000ba89  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ba90  mov     ecx, 40h ; '@'; unsigned __int64
0x18000ba95  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ba9a  mov     rbx, rax
0x18000ba9d  test    rax, rax
0x18000baa0  jz      short loc_18000BAC7
0x18000baa2  and     dword ptr [rax+28h], 0
0x18000baa6  xor     eax, eax
0x18000baa8  mov     [rbx+30h], rax
0x18000baac  mov     [rbx+38h], rax
0x18000bab0  and     [rbx], rax
0x18000bab3  and     [rbx+8], rax
0x18000bab7  and     [rbx+10h], rax
0x18000babb  and     [rbx+18h], rax
0x18000babf  and     [rbx+20h], eax
0x18000bac2  and     [rbx+24h], eax
0x18000bac5  jmp     short loc_18000BAC9
0x18000bac7  xor     ebx, ebx
0x18000bac9  test    rbx, rbx
0x18000bacc  jnz     short loc_18000BAD3
0x18000bace  lea     edi, [rbx+8]
0x18000bad1  jmp     short loc_18000BB3F
0x18000bad3  mov     rdx, rdi; unsigned __int16 *
0x18000bad6  mov     rcx, rbx; this
0x18000bad9  call    ?Initialize@CWdsMetadataEntry@@QEAAKPEBG@Z; CWdsMetadataEntry::Initialize(ushort const *)
0x18000bade  mov     r9d, 1077h; unsigned int
0x18000bae4  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000baeb  mov     ecx, eax; unsigned int
0x18000baed  mov     edi, eax
0x18000baef  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000baf4  test    eax, eax
0x18000baf6  jnz     short loc_18000BB21
0x18000baf8  mov     rdx, rbx; struct CWdsMetadataEntry *
0x18000bafb  mov     rcx, rsi; this
0x18000bafe  call    ?AddEntry@CWdsMetadata@@AEAAKPEAVCWdsMetadataEntry@@@Z; CWdsMetadata::AddEntry(CWdsMetadataEntry *)
0x18000bb03  mov     r9d, 107Ah; unsigned int
0x18000bb09  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18000bb10  mov     ecx, eax; unsigned int
0x18000bb12  mov     edi, eax
0x18000bb14  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000bb19  neg     eax
0x18000bb1b  sbb     rcx, rcx
0x18000bb1e  and     rbx, rcx
0x18000bb21  test    rbx, rbx
0x18000bb24  jz      short loc_18000BB3F
0x18000bb26  mov     rcx, rbx; this
0x18000bb29  call    ?Shutdown@CWdsMetadataEntry@@QEAAXXZ; CWdsMetadataEntry::Shutdown(void)
0x18000bb2e  lea     rcx, [rbx+28h]; this
0x18000bb32  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x18000bb37  mov     rcx, rbx; Block
0x18000bb3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bb3f  mov     rbx, [rsp+28h+arg_0]
0x18000bb44  mov     eax, edi
0x18000bb46  mov     rsi, [rsp+28h+arg_8]
0x18000bb4b  add     rsp, 20h
0x18000bb4f  pop     rdi
0x18000bb50  retn
```
