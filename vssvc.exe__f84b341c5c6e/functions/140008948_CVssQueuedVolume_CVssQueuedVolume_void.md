# CVssQueuedVolume::~CVssQueuedVolume(void)

- ea: `0x140008948`
- end: `0x140008a08`
- name: `??1CVssQueuedVolume@@QEAA@XZ`
- size: `192`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400a094c`

## callees

- `0x140008450`
- `0x140008948`
- `0x140008f7c`
- `0x140018130`
- `0x140056760`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400089a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400089ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400089a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400089ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008968`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000897a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000898c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008968`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000897a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000898c`

## pseudocode

```c
void __fastcall CVssQueuedVolume::~CVssQueuedVolume(LPVOID *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *this = &CVssQueuedVolume::`vftable';
  CVssWorkerThread::FinalReleaseWorkerThreadObject((CVssWorkerThread *)this);
  CoTaskMemFree(this[9]);
  this[9] = 0;
  CoTaskMemFree(this[10]);
  this[10] = 0;
  CoTaskMemFree(this[11]);
  this[11] = 0;
  v2 = this[5];
  if ( v2 )
    CloseHandle(v2);
  this[5] = 0;
  v3 = this[8];
  if ( v3 )
    CloseHandle(v3);
  this[8] = 0;
  this[32] = 0;
  CVssDiag::~CVssDiag((CVssDiag *)(this + 46));
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)(this + 32));
  CVssIOCTLChannel::~CVssIOCTLChannel((CVssIOCTLChannel *)(this + 18));
  CVssWorkerThread::~CVssWorkerThread((CVssWorkerThread *)this);
}

```

## disassembly

```asm
0x140008948  mov     [rsp+arg_0], rbx
0x14000894d  push    rdi
0x14000894e  sub     rsp, 20h
0x140008952  mov     rdi, rcx
0x140008955  lea     rax, ??_7CVssQueuedVolume@@6B@; const CVssQueuedVolume::`vftable'
0x14000895c  mov     [rcx], rax
0x14000895f  call    ?FinalReleaseWorkerThreadObject@CVssWorkerThread@@IEAAXXZ; CVssWorkerThread::FinalReleaseWorkerThreadObject(void)
0x140008964  mov     rcx, [rdi+48h]; pv
0x140008968  call    cs:__imp_CoTaskMemFree
0x14000896e  mov     qword ptr [rdi+48h], 0
0x140008976  mov     rcx, [rdi+50h]; pv
0x14000897a  call    cs:__imp_CoTaskMemFree
0x140008980  mov     qword ptr [rdi+50h], 0
0x140008988  mov     rcx, [rdi+58h]; pv
0x14000898c  call    cs:__imp_CoTaskMemFree
0x140008992  mov     qword ptr [rdi+58h], 0
0x14000899a  mov     rcx, [rdi+28h]; hObject
0x14000899e  test    rcx, rcx
0x1400089a1  jz      short loc_1400089A9
0x1400089a3  call    cs:__imp_CloseHandle
0x1400089a9  mov     qword ptr [rdi+28h], 0
0x1400089b1  mov     rcx, [rdi+40h]; hObject
0x1400089b5  test    rcx, rcx
0x1400089b8  jz      short loc_1400089C0
0x1400089ba  call    cs:__imp_CloseHandle
0x1400089c0  mov     qword ptr [rdi+40h], 0
0x1400089c8  lea     rbx, [rdi+100h]
0x1400089cf  mov     qword ptr [rbx], 0
0x1400089d6  lea     rcx, [rdi+170h]; this
0x1400089dd  call    ??1CVssDiag@@QEAA@XZ; CVssDiag::~CVssDiag(void)
0x1400089e2  mov     rcx, rbx; this
0x1400089e5  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x1400089ea  lea     rcx, [rdi+90h]; this
0x1400089f1  call    ??1CVssIOCTLChannel@@QEAA@XZ; CVssIOCTLChannel::~CVssIOCTLChannel(void)
0x1400089f6  mov     rcx, rdi; this
0x1400089f9  mov     rbx, [rsp+28h+arg_0]
0x1400089fe  add     rsp, 20h
0x140008a02  pop     rdi
0x140008a03  jmp     ??1CVssWorkerThread@@IEAA@XZ; CVssWorkerThread::~CVssWorkerThread(void)
```
