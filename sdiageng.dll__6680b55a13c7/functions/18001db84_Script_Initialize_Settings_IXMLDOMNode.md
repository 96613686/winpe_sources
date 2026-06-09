# Script::Initialize(Settings *,IXMLDOMNode *)

- ea: `0x18001db84`
- end: `0x18001dc1f`
- name: `?Initialize@Script@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 **this, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001be18`
- `0x18001c5ac`
- `0x18001d0f0`

## callees

- `0x18001db84`
- `0x18001dc28`
- `0x180026fa0`
- `0x1800280f8`

## string_xrefs

- `0x18001dbc8`: `<?xml version="1.0" encoding="utf-8"?><DetailedInformation/>`

## pseudocode

```c
__int64 __fastcall Script::Initialize(
        struct IXMLDOMDocument2 **this,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  int v5; // r9d
  int v6; // r8d
  unsigned int v7; // ebx
  int v8; // eax

  if ( !a2 )
  {
    v5 = -2147024809;
    v6 = 75;
    v7 = -2147024809;
LABEL_10:
    SdpDebugTrace(1u, L"Script::Initialize", v6, v5);
    return v7;
  }
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 76;
    v7 = -2147024809;
    goto LABEL_10;
  }
  *this = a2;
  v8 = SdpXmlCreate((OLECHAR *)L"<?xml version=\"1.0\" encoding=\"utf-8\"?><DetailedInformation/>", this + 6);
  v7 = v8;
  if ( v8 < 0 )
  {
    v6 = 81;
LABEL_9:
    v5 = v8;
    goto LABEL_10;
  }
  v8 = Script::ParseScriptXml((Script *)this, a3);
  v7 = v8;
  if ( v8 < 0 )
  {
    v6 = 84;
    goto LABEL_9;
  }
  return v7;
}

```

## disassembly

```asm
0x18001db84  mov     [rsp+arg_0], rbx
0x18001db89  mov     [rsp+arg_8], rsi
0x18001db8e  push    rdi
0x18001db8f  sub     rsp, 20h
0x18001db93  mov     rsi, r8
0x18001db96  mov     rdi, rcx
0x18001db99  test    rdx, rdx
0x18001db9c  jnz     short loc_18001DBAD
0x18001db9e  mov     r9d, 80070057h
0x18001dba4  lea     r8d, [rdx+4Bh]
0x18001dba8  mov     ebx, r9d
0x18001dbab  jmp     short loc_18001DBFC
0x18001dbad  test    rsi, rsi
0x18001dbb0  jnz     short loc_18001DBC1
0x18001dbb2  mov     r9d, 80070057h
0x18001dbb8  lea     r8d, [rsi+4Ch]
0x18001dbbc  mov     ebx, r9d
0x18001dbbf  jmp     short loc_18001DBFC
0x18001dbc1  mov     [rcx], rdx
0x18001dbc4  lea     rdx, [rcx+30h]; struct IXMLDOMDocument2 **
0x18001dbc8  lea     rcx, aXmlVersion10En_20; "<?xml version=\"1.0\" encoding=\"utf-8"...
0x18001dbcf  call    ?SdpXmlCreate@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlCreate(ushort const *,IXMLDOMDocument2 * *)
0x18001dbd4  mov     ebx, eax
0x18001dbd6  test    eax, eax
0x18001dbd8  jns     short loc_18001DBE2
0x18001dbda  mov     r8d, 51h ; 'Q'
0x18001dbe0  jmp     short loc_18001DBF9
0x18001dbe2  mov     rdx, rsi; struct IXMLDOMNode *
0x18001dbe5  mov     rcx, rdi; this
0x18001dbe8  call    ?ParseScriptXml@Script@@AEAAJPEAUIXMLDOMNode@@@Z; Script::ParseScriptXml(IXMLDOMNode *)
0x18001dbed  mov     ebx, eax
0x18001dbef  test    eax, eax
0x18001dbf1  jns     short loc_18001DC0D
0x18001dbf3  mov     r8d, 54h ; 'T'; int
0x18001dbf9  mov     r9d, eax; int
0x18001dbfc  lea     rdx, aScriptInitiali; "Script::Initialize"
0x18001dc03  mov     ecx, 1; Level
0x18001dc08  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001dc0d  mov     rsi, [rsp+28h+arg_8]
0x18001dc12  mov     eax, ebx
0x18001dc14  mov     rbx, [rsp+28h+arg_0]
0x18001dc19  add     rsp, 20h
0x18001dc1d  pop     rdi
0x18001dc1e  retn
```
