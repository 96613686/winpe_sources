# Troubleshooter::Initialize(Settings *,IXMLDOMNode *)

- ea: `0x18001bdac`
- end: `0x18001be0f`
- name: `?Initialize@Troubleshooter@@QEAAJPEAVSettings@@PEAUIXMLDOMNode@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(Troubleshooter *this, struct Settings *, struct IXMLDOMNode *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016460`
- `0x18001a36c`

## callees

- `0x18001bdac`
- `0x18001bf34`
- `0x180026fa0`

## pseudocode

```c
__int64 __fastcall Troubleshooter::Initialize(Troubleshooter *this, struct Settings *a2, struct IXMLDOMNode *a3)
{
  int v3; // r9d
  int v4; // r8d
  unsigned int v5; // ebx
  int v6; // eax

  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 67;
    v5 = -2147024809;
LABEL_7:
    SdpDebugTrace(1u, L"Troubleshooter::Initialize", v4, v3);
    return v5;
  }
  if ( !a3 )
  {
    v3 = -2147024809;
    v4 = 68;
    v5 = -2147024809;
    goto LABEL_7;
  }
  *(_QWORD *)this = a2;
  v6 = Troubleshooter::ParseTroubleshooterXml(this, a3);
  v5 = v6;
  if ( v6 < 0 )
  {
    v3 = v6;
    v4 = 73;
    goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x18001bdac  push    rbx
0x18001bdae  sub     rsp, 20h
0x18001bdb2  test    rdx, rdx
0x18001bdb5  jnz     short loc_18001BDC6
0x18001bdb7  mov     r9d, 80070057h
0x18001bdbd  lea     r8d, [rdx+43h]
0x18001bdc1  mov     ebx, r9d
0x18001bdc4  jmp     short loc_18001BDF6
0x18001bdc6  test    r8, r8
0x18001bdc9  jnz     short loc_18001BDDC
0x18001bdcb  mov     r9d, 80070057h
0x18001bdd1  mov     r8d, 44h ; 'D'
0x18001bdd7  mov     ebx, r9d
0x18001bdda  jmp     short loc_18001BDF6
0x18001bddc  mov     [rcx], rdx
0x18001bddf  mov     rdx, r8; struct IXMLDOMNode *
0x18001bde2  call    ?ParseTroubleshooterXml@Troubleshooter@@AEAAJPEAUIXMLDOMNode@@@Z; Troubleshooter::ParseTroubleshooterXml(IXMLDOMNode *)
0x18001bde7  mov     ebx, eax
0x18001bde9  test    eax, eax
0x18001bdeb  jns     short loc_18001BE07
0x18001bded  mov     r9d, eax; int
0x18001bdf0  mov     r8d, 49h ; 'I'; int
0x18001bdf6  lea     rdx, aTroubleshooter_0; "Troubleshooter::Initialize"
0x18001bdfd  mov     ecx, 1; Level
0x18001be02  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18001be07  mov     eax, ebx
0x18001be09  add     rsp, 20h
0x18001be0d  pop     rbx
0x18001be0e  retn
```
