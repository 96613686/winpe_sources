# ColumnAttributeOutType(_XMRW_OPEN_CONTEXT *,_UNICODE_STRING &,_TRACERPT_COLUMN *)

- ea: `0x140030cf8`
- end: `0x140031234`
- name: `?ColumnAttributeOutType@@YAKPEAU_XMRW_OPEN_CONTEXT@@AEAU_UNICODE_STRING@@PEAU_TRACERPT_COLUMN@@@Z`
- size: `1340`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *, struct _UNICODE_STRING *, struct _TRACERPT_COLUMN *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400315c8`

## callees

- `0x140016808`
- `0x140030cf8`

## string_xrefs

- `0x1400311cf`: `win:Xml`

## pseudocode

```c
__int64 __fastcall ColumnAttributeOutType(
        struct _XMRW_OPEN_CONTEXT *a1,
        struct _UNICODE_STRING *a2,
        struct _TRACERPT_COLUMN *a3)
{
  struct _UNICODE_STRING v6; // [rsp+20h] [rbp-10h] BYREF

  v6 = *a2;
  if ( !EqualString(&v6, L"xs:string", 0) )
  {
    *((_WORD *)a3 + 182) = 1;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:dateTime", 0) )
  {
    *((_WORD *)a3 + 182) = 2;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:byte", 0) )
  {
    *((_WORD *)a3 + 182) = 3;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:unsignedByte", 0) )
  {
    *((_WORD *)a3 + 182) = 4;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:short", 0) )
  {
    *((_WORD *)a3 + 182) = 5;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:unsignedShort", 0) )
  {
    *((_WORD *)a3 + 182) = 6;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:int", 0) )
  {
    *((_WORD *)a3 + 182) = 7;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:unsignedInt", 0) )
  {
    *((_WORD *)a3 + 182) = 8;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:long", 0) )
  {
    *((_WORD *)a3 + 182) = 9;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:unsignedLong", 0) )
  {
    *((_WORD *)a3 + 182) = 10;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:float", 0) )
  {
    *((_WORD *)a3 + 182) = 11;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:double", 0) )
  {
    *((_WORD *)a3 + 182) = 12;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:boolean", 0) )
  {
    *((_WORD *)a3 + 182) = 13;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:GUID", 0) )
  {
    *((_WORD *)a3 + 182) = 14;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"xs:hexBinary", 0) )
  {
    *((_WORD *)a3 + 182) = 15;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:HexInt8", 0) )
  {
    *((_WORD *)a3 + 182) = 16;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:HexInt16", 0) )
  {
    *((_WORD *)a3 + 182) = 17;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:HexInt32", 0) )
  {
    *((_WORD *)a3 + 182) = 18;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:HexInt64", 0) )
  {
    *((_WORD *)a3 + 182) = 19;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:PID", 0) )
  {
    *((_WORD *)a3 + 182) = 20;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:TID", 0) )
  {
    *((_WORD *)a3 + 182) = 21;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:Port", 0) )
  {
    *((_WORD *)a3 + 182) = 22;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:IPv4", 0) )
  {
    *((_WORD *)a3 + 182) = 23;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:IPv6", 0) )
  {
    *((_WORD *)a3 + 182) = 24;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:SocketAddress", 0) )
  {
    *((_WORD *)a3 + 182) = 25;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:CIMDateTime", 0) )
  {
    *((_WORD *)a3 + 182) = 26;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:ETWTIME", 0) )
  {
    *((_WORD *)a3 + 182) = 27;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:Xml", 0) )
  {
    *((_WORD *)a3 + 182) = 28;
    return 0;
  }
  v6 = *a2;
  if ( !EqualString(&v6, L"win:ErrorCode", 0) )
  {
    *((_WORD *)a3 + 182) = 29;
    return 0;
  }
  return 3221745184LL;
}

```

## disassembly

```asm
0x140030cf8  mov     [rsp-8+arg_0], rbx
0x140030cfd  mov     [rsp-8+arg_8], rdi
0x140030d02  push    rbp
0x140030d03  mov     rbp, rsp
0x140030d06  sub     rsp, 30h
0x140030d0a  movups  xmm0, xmmword ptr [rdx]
0x140030d0d  mov     rbx, r8
0x140030d10  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030d14  mov     rdi, rdx
0x140030d17  xor     r8d, r8d; unsigned __int8
0x140030d1a  lea     rdx, aXsString; "xs:string"
0x140030d21  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030d26  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030d2b  test    al, al
0x140030d2d  jnz     short loc_140030D3D
0x140030d2f  mov     word ptr [rbx+16Ch], 1
0x140030d38  jmp     loc_14003121B
0x140030d3d  movups  xmm0, xmmword ptr [rdi]
0x140030d40  xor     r8d, r8d; unsigned __int8
0x140030d43  lea     rdx, aXsDatetime; "xs:dateTime"
0x140030d4a  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030d4e  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030d53  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030d58  test    al, al
0x140030d5a  jnz     short loc_140030D6A
0x140030d5c  mov     word ptr [rbx+16Ch], 2
0x140030d65  jmp     loc_14003121B
0x140030d6a  movups  xmm0, xmmword ptr [rdi]
0x140030d6d  xor     r8d, r8d; unsigned __int8
0x140030d70  lea     rdx, aXsByte; "xs:byte"
0x140030d77  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030d7b  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030d80  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030d85  test    al, al
0x140030d87  jnz     short loc_140030D97
0x140030d89  mov     word ptr [rbx+16Ch], 3
0x140030d92  jmp     loc_14003121B
0x140030d97  movups  xmm0, xmmword ptr [rdi]
0x140030d9a  xor     r8d, r8d; unsigned __int8
0x140030d9d  lea     rdx, aXsUnsignedbyte; "xs:unsignedByte"
0x140030da4  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030da8  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030dad  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030db2  test    al, al
0x140030db4  jnz     short loc_140030DC4
0x140030db6  mov     word ptr [rbx+16Ch], 4
0x140030dbf  jmp     loc_14003121B
0x140030dc4  movups  xmm0, xmmword ptr [rdi]
0x140030dc7  xor     r8d, r8d; unsigned __int8
0x140030dca  lea     rdx, aXsShort; "xs:short"
0x140030dd1  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030dd5  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030dda  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030ddf  test    al, al
0x140030de1  jnz     short loc_140030DF1
0x140030de3  mov     word ptr [rbx+16Ch], 5
0x140030dec  jmp     loc_14003121B
0x140030df1  movups  xmm0, xmmword ptr [rdi]
0x140030df4  xor     r8d, r8d; unsigned __int8
0x140030df7  lea     rdx, aXsUnsignedshor; "xs:unsignedShort"
0x140030dfe  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030e02  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030e07  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030e0c  test    al, al
0x140030e0e  jnz     short loc_140030E1E
0x140030e10  mov     word ptr [rbx+16Ch], 6
0x140030e19  jmp     loc_14003121B
0x140030e1e  movups  xmm0, xmmword ptr [rdi]
0x140030e21  xor     r8d, r8d; unsigned __int8
0x140030e24  lea     rdx, aXsInt; "xs:int"
0x140030e2b  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030e2f  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030e34  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030e39  test    al, al
0x140030e3b  jnz     short loc_140030E4B
0x140030e3d  mov     word ptr [rbx+16Ch], 7
0x140030e46  jmp     loc_14003121B
0x140030e4b  movups  xmm0, xmmword ptr [rdi]
0x140030e4e  xor     r8d, r8d; unsigned __int8
0x140030e51  lea     rdx, aXsUnsignedint; "xs:unsignedInt"
0x140030e58  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030e5c  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030e61  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030e66  test    al, al
0x140030e68  jnz     short loc_140030E78
0x140030e6a  mov     word ptr [rbx+16Ch], 8
0x140030e73  jmp     loc_14003121B
0x140030e78  movups  xmm0, xmmword ptr [rdi]
0x140030e7b  xor     r8d, r8d; unsigned __int8
0x140030e7e  lea     rdx, aXsLong; "xs:long"
0x140030e85  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030e89  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030e8e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030e93  test    al, al
0x140030e95  jnz     short loc_140030EA5
0x140030e97  mov     word ptr [rbx+16Ch], 9
0x140030ea0  jmp     loc_14003121B
0x140030ea5  movups  xmm0, xmmword ptr [rdi]
0x140030ea8  xor     r8d, r8d; unsigned __int8
0x140030eab  lea     rdx, aXsUnsignedlong; "xs:unsignedLong"
0x140030eb2  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030eb6  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030ebb  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030ec0  test    al, al
0x140030ec2  jnz     short loc_140030ED2
0x140030ec4  mov     word ptr [rbx+16Ch], 0Ah
0x140030ecd  jmp     loc_14003121B
0x140030ed2  movups  xmm0, xmmword ptr [rdi]
0x140030ed5  xor     r8d, r8d; unsigned __int8
0x140030ed8  lea     rdx, aXsFloat; "xs:float"
0x140030edf  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030ee3  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030ee8  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030eed  test    al, al
0x140030eef  jnz     short loc_140030EFF
0x140030ef1  mov     word ptr [rbx+16Ch], 0Bh
0x140030efa  jmp     loc_14003121B
0x140030eff  movups  xmm0, xmmword ptr [rdi]
0x140030f02  xor     r8d, r8d; unsigned __int8
0x140030f05  lea     rdx, aXsDouble; "xs:double"
0x140030f0c  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030f10  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030f15  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030f1a  test    al, al
0x140030f1c  jnz     short loc_140030F2C
0x140030f1e  mov     word ptr [rbx+16Ch], 0Ch
0x140030f27  jmp     loc_14003121B
0x140030f2c  movups  xmm0, xmmword ptr [rdi]
0x140030f2f  xor     r8d, r8d; unsigned __int8
0x140030f32  lea     rdx, aXsBoolean; "xs:boolean"
0x140030f39  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030f3d  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030f42  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030f47  test    al, al
0x140030f49  jnz     short loc_140030F59
0x140030f4b  mov     word ptr [rbx+16Ch], 0Dh
0x140030f54  jmp     loc_14003121B
0x140030f59  movups  xmm0, xmmword ptr [rdi]
0x140030f5c  xor     r8d, r8d; unsigned __int8
0x140030f5f  lea     rdx, aXsGuid; "xs:GUID"
0x140030f66  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030f6a  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030f6f  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030f74  test    al, al
0x140030f76  jnz     short loc_140030F86
0x140030f78  mov     word ptr [rbx+16Ch], 0Eh
0x140030f81  jmp     loc_14003121B
0x140030f86  movups  xmm0, xmmword ptr [rdi]
0x140030f89  xor     r8d, r8d; unsigned __int8
0x140030f8c  lea     rdx, aXsHexbinary; "xs:hexBinary"
0x140030f93  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030f97  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030f9c  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030fa1  test    al, al
0x140030fa3  jnz     short loc_140030FB3
0x140030fa5  mov     word ptr [rbx+16Ch], 0Fh
0x140030fae  jmp     loc_14003121B
0x140030fb3  movups  xmm0, xmmword ptr [rdi]
0x140030fb6  xor     r8d, r8d; unsigned __int8
0x140030fb9  lea     rdx, aWinHexint8; "win:HexInt8"
0x140030fc0  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030fc4  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030fc9  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030fce  test    al, al
0x140030fd0  jnz     short loc_140030FE0
0x140030fd2  mov     word ptr [rbx+16Ch], 10h
0x140030fdb  jmp     loc_14003121B
0x140030fe0  movups  xmm0, xmmword ptr [rdi]
0x140030fe3  xor     r8d, r8d; unsigned __int8
0x140030fe6  lea     rdx, aWinHexint16; "win:HexInt16"
0x140030fed  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140030ff1  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140030ff6  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140030ffb  test    al, al
0x140030ffd  jnz     short loc_14003100D
0x140030fff  mov     word ptr [rbx+16Ch], 11h
0x140031008  jmp     loc_14003121B
0x14003100d  movups  xmm0, xmmword ptr [rdi]
0x140031010  xor     r8d, r8d; unsigned __int8
0x140031013  lea     rdx, aWinHexint32; "win:HexInt32"
0x14003101a  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003101e  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031023  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031028  test    al, al
0x14003102a  jnz     short loc_14003103A
0x14003102c  mov     word ptr [rbx+16Ch], 12h
0x140031035  jmp     loc_14003121B
0x14003103a  movups  xmm0, xmmword ptr [rdi]
0x14003103d  xor     r8d, r8d; unsigned __int8
0x140031040  lea     rdx, aWinHexint64; "win:HexInt64"
0x140031047  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003104b  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031050  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031055  test    al, al
0x140031057  jnz     short loc_140031067
0x140031059  mov     word ptr [rbx+16Ch], 13h
0x140031062  jmp     loc_14003121B
0x140031067  movups  xmm0, xmmword ptr [rdi]
0x14003106a  xor     r8d, r8d; unsigned __int8
0x14003106d  lea     rdx, aWinPid; "win:PID"
0x140031074  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031078  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003107d  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031082  test    al, al
0x140031084  jnz     short loc_140031094
0x140031086  mov     word ptr [rbx+16Ch], 14h
0x14003108f  jmp     loc_14003121B
0x140031094  movups  xmm0, xmmword ptr [rdi]
0x140031097  xor     r8d, r8d; unsigned __int8
0x14003109a  lea     rdx, aWinTid; "win:TID"
0x1400310a1  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400310a5  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400310aa  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400310af  test    al, al
0x1400310b1  jnz     short loc_1400310C1
0x1400310b3  mov     word ptr [rbx+16Ch], 15h
0x1400310bc  jmp     loc_14003121B
0x1400310c1  movups  xmm0, xmmword ptr [rdi]
0x1400310c4  xor     r8d, r8d; unsigned __int8
0x1400310c7  lea     rdx, aWinPort; "win:Port"
0x1400310ce  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400310d2  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400310d7  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400310dc  test    al, al
0x1400310de  jnz     short loc_1400310EE
0x1400310e0  mov     word ptr [rbx+16Ch], 16h
0x1400310e9  jmp     loc_14003121B
0x1400310ee  movups  xmm0, xmmword ptr [rdi]
0x1400310f1  xor     r8d, r8d; unsigned __int8
0x1400310f4  lea     rdx, aWinIpv4; "win:IPv4"
0x1400310fb  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400310ff  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031104  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031109  test    al, al
0x14003110b  jnz     short loc_14003111B
0x14003110d  mov     word ptr [rbx+16Ch], 17h
0x140031116  jmp     loc_14003121B
0x14003111b  movups  xmm0, xmmword ptr [rdi]
0x14003111e  xor     r8d, r8d; unsigned __int8
0x140031121  lea     rdx, aWinIpv6; "win:IPv6"
0x140031128  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x14003112c  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031131  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031136  test    al, al
0x140031138  jnz     short loc_140031148
0x14003113a  mov     word ptr [rbx+16Ch], 18h
0x140031143  jmp     loc_14003121B
0x140031148  movups  xmm0, xmmword ptr [rdi]
0x14003114b  xor     r8d, r8d; unsigned __int8
0x14003114e  lea     rdx, aWinSocketaddre; "win:SocketAddress"
0x140031155  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031159  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003115e  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031163  test    al, al
0x140031165  jnz     short loc_140031175
0x140031167  mov     word ptr [rbx+16Ch], 19h
0x140031170  jmp     loc_14003121B
0x140031175  movups  xmm0, xmmword ptr [rdi]
0x140031178  xor     r8d, r8d; unsigned __int8
0x14003117b  lea     rdx, aWinCimdatetime; "win:CIMDateTime"
0x140031182  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031186  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x14003118b  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x140031190  test    al, al
0x140031192  jnz     short loc_14003119F
0x140031194  mov     word ptr [rbx+16Ch], 1Ah
0x14003119d  jmp     short loc_14003121B
0x14003119f  movups  xmm0, xmmword ptr [rdi]
0x1400311a2  xor     r8d, r8d; unsigned __int8
0x1400311a5  lea     rdx, aWinEtwtime; "win:ETWTIME"
0x1400311ac  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400311b0  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400311b5  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400311ba  test    al, al
0x1400311bc  jnz     short loc_1400311C9
0x1400311be  mov     word ptr [rbx+16Ch], 1Bh
0x1400311c7  jmp     short loc_14003121B
0x1400311c9  movups  xmm0, xmmword ptr [rdi]
0x1400311cc  xor     r8d, r8d; unsigned __int8
0x1400311cf  lea     rdx, aWinXml; "win:Xml"
0x1400311d6  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x1400311da  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x1400311df  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x1400311e4  test    al, al
0x1400311e6  jnz     short loc_1400311F3
0x1400311e8  mov     word ptr [rbx+16Ch], 1Ch
0x1400311f1  jmp     short loc_14003121B
0x1400311f3  movups  xmm0, xmmword ptr [rdi]
0x1400311f6  xor     r8d, r8d; unsigned __int8
0x1400311f9  lea     rdx, aWinErrorcode; "win:ErrorCode"
0x140031200  lea     rcx, [rbp+var_10]; struct _UNICODE_STRING
0x140031204  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140031209  call    ?EqualString@@YAEU_UNICODE_STRING@@PEAGE@Z; EqualString(_UNICODE_STRING,ushort *,uchar)
0x14003120e  test    al, al
0x140031210  jnz     short loc_14003121F
0x140031212  mov     word ptr [rbx+16Ch], 1Dh
0x14003121b  xor     eax, eax
0x14003121d  jmp     short loc_140031224
0x14003121f  mov     eax, 0C007EE20h
0x140031224  mov     rbx, [rsp+30h+arg_0]
  ... truncated ...
```
