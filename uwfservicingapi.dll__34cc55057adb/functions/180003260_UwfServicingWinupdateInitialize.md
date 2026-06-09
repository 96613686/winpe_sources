# UwfServicingWinupdateInitialize

- ea: `0x180003260`
- end: `0x1800032bd`
- name: `UwfServicingWinupdateInitialize`
- size: `93`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x180001a38`
- `0x180003260`
- `0x180003c6c`

## pseudocode

```c
__int64 UwfServicingWinupdateInitialize()
{
  UWFUpdateAgent *v0; // rax

  qword_18000C840 = 0;
  v0 = (UWFUpdateAgent *)operator new(0x18u);
  if ( v0 )
  {
    *((_QWORD *)v0 + 1) = 0;
    *(_QWORD *)v0 = &UWFUpdateAgent::`vftable';
    *((_QWORD *)v0 + 2) = 0;
    qword_18000C840 = v0;
    return UWFUpdateAgent::Initialize((UWFUpdateAgent *)&UWFUpdateAgent::`vftable');
  }
  else
  {
    qword_18000C840 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180003260  sub     rsp, 28h
0x180003264  mov     ecx, 18h; Size
0x180003269  mov     cs:qword_18000C840, 0
0x180003274  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003279  test    rax, rax
0x18000327c  jz      short loc_1800032A8
0x18000327e  lea     rcx, ??_7UWFUpdateAgent@@6B@; this
0x180003285  mov     qword ptr [rax+8], 0
0x18000328d  mov     [rax], rcx
0x180003290  mov     qword ptr [rax+10h], 0
0x180003298  mov     cs:qword_18000C840, rax
0x18000329f  add     rsp, 28h
0x1800032a3  jmp     ?Initialize@UWFUpdateAgent@@QEAAJXZ; UWFUpdateAgent::Initialize(void)
0x1800032a8  mov     cs:qword_18000C840, 0
0x1800032b3  mov     eax, 8007000Eh
0x1800032b8  add     rsp, 28h
0x1800032bc  retn
```
