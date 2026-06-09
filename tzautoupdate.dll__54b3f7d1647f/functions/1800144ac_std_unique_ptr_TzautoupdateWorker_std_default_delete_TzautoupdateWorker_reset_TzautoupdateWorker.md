# std::unique_ptr<TzautoupdateWorker,std::default_delete<TzautoupdateWorker>>::reset(TzautoupdateWorker *)

- ea: `0x1800144ac`
- end: `0x1800144d7`
- name: `?reset@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@QEAAXPEAVTzautoupdateWorker@@@Z`
- size: `43`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800140a0`
- `0x1800143a0`

## callees

- `0x18000acdc`
- `0x1800144ac`

## pseudocode

```c
void __fastcall std::unique_ptr<TzautoupdateWorker>::reset(__int64 a1, __int64 a2)
{
  if ( a2 != gTzautoupdateWorker )
  {
    std::unique_ptr<TzautoupdateWorker>::_Delete((TzautoupdateWorker **)&gTzautoupdateWorker);
    gTzautoupdateWorker = a2;
  }
}

```

## disassembly

```asm
0x1800144ac  push    rbx
0x1800144ae  sub     rsp, 20h
0x1800144b2  cmp     rdx, cs:?gTzautoupdateWorker@@3V?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@A; std::unique_ptr<TzautoupdateWorker> gTzautoupdateWorker
0x1800144b9  mov     rbx, rdx
0x1800144bc  jz      short loc_1800144D1
0x1800144be  lea     rcx, ?gTzautoupdateWorker@@3V?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@A; std::unique_ptr<TzautoupdateWorker> gTzautoupdateWorker
0x1800144c5  call    ?_Delete@?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@AEAAXXZ; std::unique_ptr<TzautoupdateWorker>::_Delete(void)
0x1800144ca  mov     cs:?gTzautoupdateWorker@@3V?$unique_ptr@VTzautoupdateWorker@@U?$default_delete@VTzautoupdateWorker@@@std@@@std@@A, rbx; std::unique_ptr<TzautoupdateWorker> gTzautoupdateWorker
0x1800144d1  add     rsp, 20h
0x1800144d5  pop     rbx
0x1800144d6  retn
```
