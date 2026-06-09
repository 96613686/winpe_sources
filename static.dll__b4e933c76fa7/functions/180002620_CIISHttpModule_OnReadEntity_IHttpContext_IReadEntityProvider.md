# CIISHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002620`
- end: `0x180002639`
- name: `?OnReadEntity@CIISHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800028e0`

## pseudocode

```c
__int64 __fastcall CIISHttpModule::OnReadEntity(
        __int64 a1,
        struct IHttpContext *a2,
        void (__fastcall ***a3)(_QWORD, __int64))
{
  __int64 v4; // [rsp+20h] [rbp-18h]

  return RequestDoWork(0x40000000, (__int64)a2, a2, a3, v4);
}

```

## disassembly

```asm
0x180002620  sub     rsp, 38h
0x180002624  mov     r9, r8
0x180002627  mov     ecx, 40000000h
0x18000262c  mov     r8, rdx
0x18000262f  call    ?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z; RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)
0x180002634  add     rsp, 38h
0x180002638  retn
```
