# CWMPRichPreviewExt::~CWMPRichPreviewExt(void)

- ea: `0x140002370`
- end: `0x140002407`
- name: `??1CWMPRichPreviewExt@@QEAA@XZ`
- size: `151`
- prototype: `void __fastcall(CWMPRichPreviewExt *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ac24`
- `0x14000ad2c`
- `0x14000c550`
- `0x14000c630`

## callees

- `0x140002370`
- `0x1400099e0`
- `0x14000d978`
- `0x14000f010`

## pseudocode

```c
void __fastcall CWMPRichPreviewExt::~CWMPRichPreviewExt(unsigned __int16 **this)
{
  _UNKNOWN **v2; // rcx
  unsigned __int16 *v3; // rcx

  v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0xCu, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
      v2 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
      WPP_SF_((TRACEHANDLE)v2[2], 0xDu, &WPP_a1620705688d36e506283508f1a041e6_Traceguids);
  }
  WString::DeleteString(this + 7);
  v3 = this[6];
  if ( v3 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v3 + 16LL))(v3);
}

```

## disassembly

```asm
0x140002370  mov     [rsp+arg_0], rbx
0x140002375  push    rdi
0x140002376  sub     rsp, 20h
0x14000237a  mov     rbx, rcx
0x14000237d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002384  lea     rdi, WPP_GLOBAL_Control
0x14000238b  cmp     rcx, rdi
0x14000238e  jz      short loc_1400023DE
0x140002390  test    byte ptr [rcx+1Ch], 1
0x140002394  jz      short loc_1400023B8
0x140002396  cmp     byte ptr [rcx+19h], 5
0x14000239a  jb      short loc_1400023B8
0x14000239c  mov     rcx, [rcx+10h]
0x1400023a0  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400023a7  mov     edx, 0Ch
0x1400023ac  call    WPP_SF_
0x1400023b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023b8  cmp     rcx, rdi
0x1400023bb  jz      short loc_1400023DE
0x1400023bd  test    byte ptr [rcx+1Ch], 1
0x1400023c1  jz      short loc_1400023DE
0x1400023c3  cmp     byte ptr [rcx+19h], 5
0x1400023c7  jb      short loc_1400023DE
0x1400023c9  mov     rcx, [rcx+10h]
0x1400023cd  lea     r8, WPP_a1620705688d36e506283508f1a041e6_Traceguids
0x1400023d4  mov     edx, 0Dh
0x1400023d9  call    WPP_SF_
0x1400023de  lea     rcx, [rbx+38h]; this
0x1400023e2  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x1400023e7  mov     rcx, [rbx+30h]
0x1400023eb  test    rcx, rcx
0x1400023ee  jz      short loc_1400023FC
0x1400023f0  mov     rax, [rcx]
0x1400023f3  mov     rax, [rax+10h]
0x1400023f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023fc  mov     rbx, [rsp+28h+arg_0]
0x140002401  add     rsp, 20h
0x140002405  pop     rdi
0x140002406  retn
```
