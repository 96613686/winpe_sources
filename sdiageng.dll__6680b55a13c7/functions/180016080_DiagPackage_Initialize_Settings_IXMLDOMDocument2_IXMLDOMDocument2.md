# DiagPackage::Initialize(Settings *,IXMLDOMDocument2 *,IXMLDOMDocument2 *)

- ea: `0x180016080`
- end: `0x180016140`
- name: `?Initialize@DiagPackage@@QEAAJPEAVSettings@@PEAUIXMLDOMDocument2@@1@Z`
- size: `192`
- prototype: `__int64 __fastcall(DiagPackage *__hidden this, struct Settings *, struct IXMLDOMDocument2 *, struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000dad4`

## callees

- `0x180016080`
- `0x180016630`
- `0x1800176dc`
- `0x180026fa0`
- `0x1800280f8`

## string_xrefs

- `0x1800160d1`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`

## pseudocode

```c
__int64 __fastcall DiagPackage::Initialize(
        DiagPackage *this,
        struct Settings *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMDocument2 *a4)
{
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  int v10; // eax
  DiagPackage *v11; // rcx
  int v12; // eax
  int v13; // eax

  if ( !a2 )
  {
    v7 = 98;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
LABEL_4:
    SdpDebugTrace(1u, L"DiagPackage::Initialize", v7, v8);
    return v9;
  }
  if ( !a3 )
  {
    v7 = 99;
    goto LABEL_3;
  }
  *(_DWORD *)this |= 1u;
  *((_QWORD *)this + 1) = a2;
  v10 = SdpXmlCreate(
          (OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>",
          (struct IXMLDOMDocument2 **)this + 16);
  v9 = v10;
  if ( v10 < 0 )
  {
    v8 = v10;
    v7 = 109;
    goto LABEL_4;
  }
  v12 = DiagPackage::ValidatePackageXml(v11, a3);
  v9 = v12;
  if ( v12 < 0 )
  {
    v8 = v12;
    v7 = 112;
    goto LABEL_4;
  }
  v13 = DiagPackage::ParsePackageXml(this, a3, a4);
  v9 = v13;
  if ( v13 < 0 )
  {
    v8 = v13;
    v7 = 115;
    goto LABEL_4;
  }
  if ( (*(_BYTE *)this & 1) == 0 )
    return 3932421;
  return v9;
}

```

## disassembly

```asm
0x180016080  push    rbx
0x180016082  push    rbp
0x180016083  push    rsi
0x180016084  push    r14
0x180016086  sub     rsp, 28h
0x18001608a  mov     r14, r9
0x18001608d  mov     rbp, r8
0x180016090  mov     rsi, rcx
0x180016093  test    rdx, rdx
0x180016096  jnz     short loc_1800160B8
0x180016098  lea     r8d, [rdx+62h]; int
0x18001609c  mov     r9d, 80070057h; int
0x1800160a2  mov     ebx, r9d
0x1800160a5  lea     rdx, aDiagpackageIni_1; "DiagPackage::Initialize"
0x1800160ac  mov     ecx, 1; Level
0x1800160b1  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800160b6  jmp     short loc_180016134
0x1800160b8  test    rbp, rbp
0x1800160bb  jnz     short loc_1800160C3
0x1800160bd  lea     r8d, [rbp+63h]
0x1800160c1  jmp     short loc_18001609C
0x1800160c3  or      dword ptr [rcx], 1
0x1800160c6  mov     [rcx+8], rdx
0x1800160ca  lea     rdx, [rcx+80h]; struct IXMLDOMDocument2 **
0x1800160d1  lea     rcx, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x1800160d8  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x1800160dd  mov     ebx, eax
0x1800160df  test    eax, eax
0x1800160e1  jns     short loc_1800160EE
0x1800160e3  mov     r9d, eax
0x1800160e6  mov     r8d, 6Dh ; 'm'
0x1800160ec  jmp     short loc_1800160A5
0x1800160ee  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x1800160f1  call    ?ValidatePackageXml@DiagPackage@@AEAAJPEAUIXMLDOMDocument2@@@Z; DiagPackage::ValidatePackageXml(IXMLDOMDocument2 *)
0x1800160f6  mov     ebx, eax
0x1800160f8  test    eax, eax
0x1800160fa  jns     short loc_180016107
0x1800160fc  mov     r9d, eax
0x1800160ff  mov     r8d, 70h ; 'p'
0x180016105  jmp     short loc_1800160A5
0x180016107  mov     r8, r14; struct IXMLDOMDocument2 *
0x18001610a  mov     rdx, rbp; struct IXMLDOMDocument2 *
0x18001610d  mov     rcx, rsi; this
0x180016110  call    ?ParsePackageXml@DiagPackage@@AEAAJPEAUIXMLDOMDocument2@@0@Z; DiagPackage::ParsePackageXml(IXMLDOMDocument2 *,IXMLDOMDocument2 *)
0x180016115  mov     ebx, eax
0x180016117  test    eax, eax
0x180016119  jns     short loc_180016129
0x18001611b  mov     r9d, eax
0x18001611e  mov     r8d, 73h ; 's'
0x180016124  jmp     loc_1800160A5
0x180016129  test    byte ptr [rsi], 1
0x18001612c  mov     eax, 3C0105h
0x180016131  cmovz   ebx, eax
0x180016134  mov     eax, ebx
0x180016136  add     rsp, 28h
0x18001613a  pop     r14
0x18001613c  pop     rsi
0x18001613d  pop     rbp
0x18001613e  pop     rbx
0x18001613f  retn
```
