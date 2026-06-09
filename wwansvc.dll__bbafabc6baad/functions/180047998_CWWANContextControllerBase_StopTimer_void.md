# CWWANContextControllerBase::StopTimer(void)

- ea: `0x180047998`
- end: `0x180047a1c`
- name: `?StopTimer@CWWANContextControllerBase@@IEAAKXZ`
- size: `132`
- prototype: `unsigned int __fastcall(CWWANContextControllerBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180046244`
- `0x18004b3d0`

## callees

- `0x180014f1c`

## import_xrefs

- `MobileNetworking!StopTimer` at `0x1800479d7`
- `MobileNetworking!StopTimer` at `0x1800479d7`
- `MobileNetworking!AcquireWriteLock` at `0x1800479c3`
- `MobileNetworking!AcquireWriteLock` at `0x1800479c3`
- `MobileNetworking!ReleaseWriteLock` at `0x1800479f4`
- `MobileNetworking!ReleaseWriteLock` at `0x1800479f4`

## string_xrefs

- `0x1800479fa`: ` Timer Stop Completed`

## pseudocode

```c
__int64 __fastcall CWWANContextControllerBase::StopTimer(CWWANContextControllerBase *this)
{
  char *v1; // rbx

  v1 = (char *)this + 8072;
  AcquireWriteLock(*((_QWORD *)this + 1022), (char *)this + 8072, "CWWANContextControllerBase::StopTimer", 356);
  StopTimer(*((_QWORD *)this + 1022), "CWWANContextControllerBase::StopTimer");
  ReleaseWriteLock(*((_QWORD *)this + 1022), v1, "CWWANContextControllerBase::StopTimer", 358);
  WwanLog::Info("CWWANContextControllerBase::StopTimer", 0, L" Timer Stop Completed");
  return 0;
}

```

## disassembly

```asm
0x180047998  mov     [rsp+arg_0], rbx
0x18004799d  push    rdi
0x18004799e  sub     rsp, 20h
0x1800479a2  lea     rbx, [rcx+1F88h]
0x1800479a9  mov     rdi, rcx
0x1800479ac  mov     rcx, [rcx+1FF0h]
0x1800479b3  lea     r8, aCwwancontextco_9; "CWWANContextControllerBase::StopTimer"
0x1800479ba  mov     rdx, rbx
0x1800479bd  mov     r9d, 164h
0x1800479c3  call    cs:__imp_AcquireWriteLock
0x1800479c9  mov     rcx, [rdi+1FF0h]
0x1800479d0  lea     rdx, aCwwancontextco_9; "CWWANContextControllerBase::StopTimer"
0x1800479d7  call    cs:__imp_StopTimer
0x1800479dd  mov     rcx, [rdi+1FF0h]
0x1800479e4  lea     r8, aCwwancontextco_9; "CWWANContextControllerBase::StopTimer"
0x1800479eb  mov     r9d, 166h
0x1800479f1  mov     rdx, rbx
0x1800479f4  call    cs:__imp_ReleaseWriteLock
0x1800479fa  lea     r8, aTimerStopCompl_0; " Timer Stop Completed"
0x180047a01  xor     edx, edx; struct _GUID *
0x180047a03  lea     rcx, aCwwancontextco_9; "CWWANContextControllerBase::StopTimer"
0x180047a0a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180047a0f  mov     rbx, [rsp+28h+arg_0]
0x180047a14  xor     eax, eax
0x180047a16  add     rsp, 20h
0x180047a1a  pop     rdi
0x180047a1b  retn
```
