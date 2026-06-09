# CGestureSubmissionJobData::~CGestureSubmissionJobData(void)

- ea: `0x18000d11c`
- end: `0x18000d17f`
- name: `??1CGestureSubmissionJobData@@UEAA@XZ`
- size: `99`
- prototype: `void __fastcall(CGestureSubmissionJobData *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d900`

## callees

- `0x1800043a4`
- `0x18000d0f0`
- `0x18000d11c`
- `0x180018a28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d15a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d15a`

## pseudocode

```c
void __fastcall CGestureSubmissionJobData::~CGestureSubmissionJobData(CGestureSubmissionJobData *this)
{
  _BYTE *v2; // rax
  __int64 i; // rcx

  *(_QWORD *)this = &CGestureSubmissionJobData::`vftable';
  CPrivateNotificationWindow::Release(*((CPrivateNotificationWindow **)this + 2));
  v2 = (_BYTE *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    for ( i = *((_QWORD *)this + 9); i; --i )
      *v2++ = 0;
    CoTaskMemFree(*((LPVOID *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 104);
  CGestureSignatureArray::~CGestureSignatureArray((CGestureSubmissionJobData *)((char *)this + 24));
}

```

## disassembly

```asm
0x18000d11c  push    rbx
0x18000d11e  sub     rsp, 20h
0x18000d122  lea     rax, ??_7CGestureSubmissionJobData@@6B@; const CGestureSubmissionJobData::`vftable'
0x18000d129  mov     rbx, rcx
0x18000d12c  mov     [rcx], rax
0x18000d12f  mov     rcx, [rcx+10h]; this
0x18000d133  call    ?Release@CPrivateNotificationWindow@@QEAAKXZ; CPrivateNotificationWindow::Release(void)
0x18000d138  mov     rax, [rbx+40h]
0x18000d13c  test    rax, rax
0x18000d13f  jz      short loc_18000D168
0x18000d141  mov     rcx, [rbx+48h]
0x18000d145  test    rcx, rcx
0x18000d148  jz      short loc_18000D156
0x18000d14a  mov     byte ptr [rax], 0
0x18000d14d  inc     rax
0x18000d150  sub     rcx, 1
0x18000d154  jnz     short loc_18000D14A
0x18000d156  mov     rcx, [rbx+40h]; pv
0x18000d15a  call    cs:__imp_CoTaskMemFree
0x18000d160  mov     qword ptr [rbx+40h], 0
0x18000d168  lea     rcx, [rbx+68h]
0x18000d16c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000d171  lea     rcx, [rbx+18h]; this
0x18000d175  add     rsp, 20h
0x18000d179  pop     rbx
0x18000d17a  jmp     ??1CGestureSignatureArray@@UEAA@XZ; CGestureSignatureArray::~CGestureSignatureArray(void)
```
