# TzautoupdateWorker::~TzautoupdateWorker(void)

- ea: `0x1800049c8`
- end: `0x180004a0f`
- name: `??1TzautoupdateWorker@@QEAA@XZ`
- size: `71`
- prototype: `void __fastcall(TzautoupdateWorker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000acdc`

## callees

- `0x180004528`
- `0x1800048ac`
- `0x1800048d8`
- `0x180010b54`
- `0x180014e28`

## pseudocode

```c
void __fastcall TzautoupdateWorker::~TzautoupdateWorker(TzautoupdateWorker *this)
{
  LocationDataSource::~LocationDataSource((TzautoupdateWorker *)((char *)this + 288));
  NitzDataSource::~NitzDataSource((TzautoupdateWorker *)((char *)this + 232));
  MccDataSource::~MccDataSource((TzautoupdateWorker *)((char *)this + 192));
  TimezoneDeterminer::~TimezoneDeterminer((TzautoupdateWorker *)((char *)this + 128));
  std::function<void (Cache::Proxy &)>::~function<void (Cache::Proxy &)>((__int64)this + 8);
}

```

## disassembly

```asm
0x1800049c8  push    rbx
0x1800049ca  sub     rsp, 20h
0x1800049ce  mov     rbx, rcx
0x1800049d1  add     rcx, 120h; this
0x1800049d8  call    ??1LocationDataSource@@QEAA@XZ; LocationDataSource::~LocationDataSource(void)
0x1800049dd  lea     rcx, [rbx+0E8h]; this
0x1800049e4  call    ??1NitzDataSource@@QEAA@XZ; NitzDataSource::~NitzDataSource(void)
0x1800049e9  lea     rcx, [rbx+0C0h]; this
0x1800049f0  call    ??1MccDataSource@@QEAA@XZ; MccDataSource::~MccDataSource(void)
0x1800049f5  lea     rcx, [rbx+80h]; this
0x1800049fc  call    ??1TimezoneDeterminer@@QEAA@XZ; TimezoneDeterminer::~TimezoneDeterminer(void)
0x180004a01  lea     rcx, [rbx+8]
0x180004a05  add     rsp, 20h
0x180004a09  pop     rbx
0x180004a0a  jmp     ??1?$function@$$A6AXAEAVProxy@Cache@@@Z@std@@QEAA@XZ; std::function<void (Cache::Proxy &)>::~function<void (Cache::Proxy &)>(void)
```
