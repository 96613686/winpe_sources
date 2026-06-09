# BinXmlReader::InternalCopyInto(BinXmlWriter &)

- ea: `0x18002fdb4`
- end: `0x18002fe76`
- name: `?InternalCopyInto@BinXmlReader@@AEAAXAEAVBinXmlWriter@@@Z`
- size: `194`
- prototype: `void __fastcall(BinXmlReader *__hidden this, struct BinXmlWriter *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800240ac`
- `0x180024428`

## callees

- `0x180004070`
- `0x180013830`
- `0x180024428`
- `0x180024a50`
- `0x18002e300`
- `0x18002fdb4`

## pseudocode

```c
void __fastcall BinXmlReader::InternalCopyInto(BinXmlReader *this, struct BinXmlWriter *a2)
{
  __int64 v4; // [rsp+20h] [rbp-50h] BYREF
  int v5; // [rsp+28h] [rbp-48h]
  __int64 v6; // [rsp+2Ch] [rbp-44h]
  char v7; // [rsp+34h] [rbp-3Ch]
  _OWORD v8[2]; // [rsp+38h] [rbp-38h] BYREF
  __int64 v9; // [rsp+58h] [rbp-18h]
  __int64 v10; // [rsp+60h] [rbp-10h]

  v4 = 0;
  v5 = -1;
  v6 = 0;
  v7 = 0;
  do
  {
    BinXmlReader::NextToken(this, (struct BinXmlToken *)&v4, 0);
    if ( HIDWORD(v6) == 12 )
    {
      v9 = *((_QWORD *)this + 11);
      v10 = *((_QWORD *)a2 + 1);
      memset(v8, 0, sizeof(v8));
      BinXmlReader::ReadTemplateDefinition(this, (struct BinXmlTemplate *)v8);
      BinXmlReader::CopyTemplateInstanceInto(this, (const struct BinXmlTemplate *)v8, this, a2);
    }
    else
    {
      BinXmlWriter::AddToken(a2, (const struct BinXmlToken *)&v4);
    }
  }
  while ( HIDWORD(v6) );
}

```

## disassembly

```asm
0x18002fdb4  mov     [rsp-8+arg_10], rbx
0x18002fdb9  mov     [rsp-8+arg_18], rdi
0x18002fdbe  push    rbp
0x18002fdbf  mov     rbp, rsp
0x18002fdc2  sub     rsp, 70h
0x18002fdc6  mov     rax, cs:__security_cookie
0x18002fdcd  xor     rax, rsp
0x18002fdd0  mov     [rbp+var_8], rax
0x18002fdd4  mov     rdi, rdx
0x18002fdd7  mov     [rbp+var_50], 0
0x18002fddf  mov     rbx, rcx
0x18002fde2  mov     [rbp+var_48], 0FFFFFFFFh
0x18002fde9  mov     [rbp+var_44], 0
0x18002fdf1  mov     [rbp+var_3C], 0
0x18002fdf5  xor     r8d, r8d; bool
0x18002fdf8  lea     rdx, [rbp+var_50]; struct BinXmlToken *
0x18002fdfc  mov     rcx, rbx; this
0x18002fdff  call    ?NextToken@BinXmlReader@@QEAAXAEAUBinXmlToken@@_N@Z; BinXmlReader::NextToken(BinXmlToken &,bool)
0x18002fe04  cmp     dword ptr [rbp+var_44+4], 0Ch
0x18002fe08  jz      short loc_18002FE18
0x18002fe0a  lea     rdx, [rbp+var_50]; struct BinXmlToken *
0x18002fe0e  mov     rcx, rdi; this
0x18002fe11  call    ?AddToken@BinXmlWriter@@QEAAXAEBUBinXmlToken@@@Z; BinXmlWriter::AddToken(BinXmlToken const &)
0x18002fe16  jmp     short loc_18002FE52
0x18002fe18  mov     rax, [rbx+58h]
0x18002fe1c  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x18002fe20  xorps   xmm0, xmm0
0x18002fe23  mov     [rbp+var_18], rax
0x18002fe27  mov     rax, [rdi+8]
0x18002fe2b  mov     rcx, rbx; this
0x18002fe2e  mov     [rbp+var_10], rax
0x18002fe32  movdqu  [rbp+var_38], xmm0
0x18002fe37  movups  [rbp+var_28], xmm0
0x18002fe3b  call    ?ReadTemplateDefinition@BinXmlReader@@QEAAXAEAVBinXmlTemplate@@@Z; BinXmlReader::ReadTemplateDefinition(BinXmlTemplate &)
0x18002fe40  mov     r9, rdi; struct BinXmlWriter *
0x18002fe43  lea     rdx, [rbp+var_38]; struct BinXmlTemplate *
0x18002fe47  mov     r8, rbx; struct UserBuffer *
0x18002fe4a  mov     rcx, rbx; this
0x18002fe4d  call    ?CopyTemplateInstanceInto@BinXmlReader@@AEAAXAEBVBinXmlTemplate@@AEAVUserBuffer@@AEAVBinXmlWriter@@@Z; BinXmlReader::CopyTemplateInstanceInto(BinXmlTemplate const &,UserBuffer &,BinXmlWriter &)
0x18002fe52  cmp     dword ptr [rbp+var_44+4], 0
0x18002fe56  jnz     short loc_18002FDF5
0x18002fe58  mov     rcx, [rbp+var_8]
0x18002fe5c  xor     rcx, rsp; StackCookie
0x18002fe5f  call    __security_check_cookie
0x18002fe64  lea     r11, [rsp+70h+var_s0]
0x18002fe69  mov     rbx, [r11+20h]
0x18002fe6d  mov     rdi, [r11+28h]
0x18002fe71  mov     rsp, r11
0x18002fe74  pop     rbp
0x18002fe75  retn
```
