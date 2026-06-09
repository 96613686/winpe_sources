# ATL::CComCritSecLock<ATL::CComFakeCriticalSection>::~CComCritSecLock<ATL::CComFakeCriticalSection>(void)

- ea: `0x18001ddcc`
- end: `0x18001ddd7`
- name: `??1?$CComCritSecLock@VCComFakeCriticalSection@ATL@@@ATL@@QEAA@XZ`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003307c`

## callees

- `0x18001ddcc`

## pseudocode

```c
void __fastcall ATL::CComCritSecLock<ATL::CComFakeCriticalSection>::~CComCritSecLock<ATL::CComFakeCriticalSection>(
        __int64 a1)
{
  if ( *(_BYTE *)(a1 + 8) )
    *(_BYTE *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x18001ddcc  cmp     byte ptr [rcx+8], 0
0x18001ddd0  jz      short locret_18001DDD6
0x18001ddd2  mov     byte ptr [rcx+8], 0
0x18001ddd6  retn
```
