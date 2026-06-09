# ATL::CComTypeInfoHolder::stringdispid::stringdispid(void)

- ea: `0x140001ff4`
- end: `0x14000200d`
- name: `??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `25`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140005ee4`

## pseudocode

```c
ATL::CComTypeInfoHolder::stringdispid *__fastcall ATL::CComTypeInfoHolder::stringdispid::stringdispid(
        ATL::CComTypeInfoHolder::stringdispid *this)
{
  ATL::CComTypeInfoHolder::stringdispid *result; // rax

  *(_QWORD *)this = 0;
  result = this;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 3) = -1;
  return result;
}

```

## disassembly

```asm
0x140001ff4  mov     qword ptr [rcx], 0
0x140001ffb  mov     rax, rcx
0x140001ffe  mov     dword ptr [rcx+8], 0
0x140002005  mov     dword ptr [rcx+0Ch], 0FFFFFFFFh
0x14000200c  retn
```
