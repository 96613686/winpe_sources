# CUsbDevice::~CUsbDevice(void)

- ea: `0x1800041b4`
- end: `0x18000420a`
- name: `??1CUsbDevice@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(CUsbDevice *__hidden this)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180004210`
- `0x180004388`
- `0x1800053e4`
- `0x1800100fa`
- `0x1800101d2`

## callees

- `0x180003c6c`
- `0x180004060`
- `0x1800040e4`
- `0x180004108`
- `0x1800041b4`

## pseudocode

```c
void __fastcall CUsbDevice::~CUsbDevice(CUsbDevice *this)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)*((_QWORD *)this + 10);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, *((_QWORD *)this + 12) - (_QWORD)v2);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 12) = 0;
  }
  std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>((_QWORD *)this + 3);
  std::unique_ptr<CHostController>::~unique_ptr<CHostController>((void **)this + 2);
  std::unique_ptr<CUsbDevice>::~unique_ptr<CUsbDevice>((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x1800041b4  push    rbx
0x1800041b6  sub     rsp, 20h
0x1800041ba  mov     rbx, rcx
0x1800041bd  mov     rcx, [rcx+50h]
0x1800041c1  test    rcx, rcx
0x1800041c4  jz      short loc_1800041EA
0x1800041c6  mov     rdx, [rbx+60h]
0x1800041ca  sub     rdx, rcx
0x1800041cd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800041d2  mov     qword ptr [rbx+50h], 0
0x1800041da  mov     qword ptr [rbx+58h], 0
0x1800041e2  mov     qword ptr [rbx+60h], 0
0x1800041ea  lea     rcx, [rbx+18h]
0x1800041ee  call    ??1?$unique_ptr@VCDevNode@@U?$default_delete@VCDevNode@@@std@@@std@@QEAA@XZ; std::unique_ptr<CDevNode>::~unique_ptr<CDevNode>(void)
0x1800041f3  lea     rcx, [rbx+10h]
0x1800041f7  call    ??1?$unique_ptr@VCHostController@@U?$default_delete@VCHostController@@@std@@@std@@QEAA@XZ; std::unique_ptr<CHostController>::~unique_ptr<CHostController>(void)
0x1800041fc  lea     rcx, [rbx+8]
0x180004200  add     rsp, 20h
0x180004204  pop     rbx
0x180004205  jmp     ??1?$unique_ptr@VCUsbDevice@@U?$default_delete@VCUsbDevice@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUsbDevice>::~unique_ptr<CUsbDevice>(void)
```
