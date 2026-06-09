# CWriteToIStream::~CWriteToIStream(void)

- ea: `0x180054110`
- end: `0x180054153`
- name: `??1CWriteToIStream@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CWriteToIStream *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800541e0`
- `0x180054d28`
- `0x18010007c`

## callees

- `0x180002db8`
- `0x180054110`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005412c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005412c`

## pseudocode

```c
void __fastcall CWriteToIStream::~CWriteToIStream(CWriteToIStream *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CWriteToIStream::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 2) = 0;
  }
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>((char *)this + 8);
  *(_QWORD *)this = &CWriteStream::`vftable';
}

```

## disassembly

```asm
0x180054110  push    rbx
0x180054112  sub     rsp, 20h
0x180054116  lea     rax, ??_7CWriteToIStream@@6B@; const CWriteToIStream::`vftable'
0x18005411d  mov     rbx, rcx
0x180054120  mov     [rcx], rax
0x180054123  mov     rcx, [rcx+10h]; pv
0x180054127  test    rcx, rcx
0x18005412a  jz      short loc_18005413A
0x18005412c  call    cs:__imp_CoTaskMemFree
0x180054132  mov     qword ptr [rbx+10h], 0
0x18005413a  lea     rcx, [rbx+8]
0x18005413e  call    ??1?$CComPtrBase@UISpObjectToken@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(void)
0x180054143  lea     rax, ??_7CWriteStream@@6B@; const CWriteStream::`vftable'
0x18005414a  mov     [rbx], rax
0x18005414d  add     rsp, 20h
0x180054151  pop     rbx
0x180054152  retn
```
