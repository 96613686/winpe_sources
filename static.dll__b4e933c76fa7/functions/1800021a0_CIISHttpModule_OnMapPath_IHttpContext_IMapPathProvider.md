# CIISHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x1800021a0`
- end: `0x1800021b9`
- name: `?OnMapPath@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800028e0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnMapPath(
        __int64 a1,
        struct IHttpContext *a2,
        void (__fastcall ***a3)(_QWORD, __int64))
{
  __int64 v4; // [rsp+20h] [rbp-18h]

  return RequestDoWork(0x80000000, (__int64)a2, a2, a3, v4);
}

```

## disassembly

```asm
0x1800021a0  sub     rsp, 38h
0x1800021a4  mov     r9, r8
0x1800021a7  mov     ecx, 80000000h
0x1800021ac  mov     r8, rdx
0x1800021af  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x1800021b4  add     rsp, 38h
0x1800021b8  retn
```
