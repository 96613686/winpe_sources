# CLoaderProcess::ValidateAndCopySection(CThemeServer *,void *,void *,CAPIDispatchSync *,void * *,void * *)

- ea: `0x18000d37c`
- end: `0x18000d427`
- name: `?ValidateAndCopySection@CLoaderProcess@@QEAAJPEAVCThemeServer@@PEAX1PEAVCAPIDispatchSync@@PEAPEAX3@Z`
- size: `171`
- prototype: `__int64 __fastcall(CLoaderProcess *__hidden this, struct CThemeServer *, void *, void *, struct CAPIDispatchSync *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x18000acc0`

## callees

- `0x1800069f4`
- `0x18000d37c`
- `0x18000d524`

## pseudocode

```c
__int64 __fastcall CLoaderProcess::ValidateAndCopySection(
        CLoaderProcess *this,
        struct CThemeServer *a2,
        void *a3,
        void *a4,
        struct CAPIDispatchSync *a5,
        void **a6,
        void **a7)
{
  HANDLE *v7; // r14
  void *ServiceStoppingEvent; // rax
  HANDLE v10; // r9
  HANDLE v11; // r10
  CThemeServer *v12; // r11
  __int64 result; // rax
  unsigned int v14; // [rsp+48h] [rbp-40h]

  v7 = (HANDLE *)((char *)this + 72);
  *a6 = 0;
  *a7 = 0;
  ServiceStoppingEvent = CAPIDispatchSync::GetServiceStoppingEvent(a5);
  result = CThemeServer::CopyTheme(
             v12,
             v11,
             (LPHANDLE)this + 8,
             v10,
             v7,
             *((unsigned __int16 **)this + 4),
             *((unsigned __int16 **)this + 5),
             *((unsigned __int16 **)this + 6),
             *((_DWORD *)this + 14),
             v14,
             *((HANDLE *)this + 3),
             ServiceStoppingEvent)
         & 0xEFFFFFFFLL;
  *((_DWORD *)this + 20) = result;
  if ( (int)result >= 0 )
  {
    *a6 = (void *)*((_QWORD *)this + 8);
    *a7 = *v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000d37c  push    rbx
0x18000d37e  push    rsi
0x18000d37f  push    rdi
0x18000d380  push    r14
0x18000d382  push    r15
0x18000d384  sub     rsp, 60h
0x18000d388  mov     rdi, [rsp+88h+arg_28]
0x18000d390  lea     r14, [rcx+48h]
0x18000d394  mov     rsi, [rsp+88h+arg_30]
0x18000d39c  mov     rbx, rcx
0x18000d39f  mov     rcx, [rsp+88h+arg_20]; struct CAPIDispatchSync *
0x18000d3a7  mov     r10, r8
0x18000d3aa  mov     r11, rdx
0x18000d3ad  mov     qword ptr [rdi], 0
0x18000d3b4  mov     qword ptr [rsi], 0
0x18000d3bb  call    ?GetServiceStoppingEvent@CAPIDispatchSync@@SAPEAXPEAV1@@Z; CAPIDispatchSync::GetServiceStoppingEvent(CAPIDispatchSync *)
0x18000d3c0  mov     [rsp+88h+var_30], rax; void *
0x18000d3c5  lea     r8, [rbx+40h]; lpTargetHandle
0x18000d3c9  mov     rax, [rbx+18h]
0x18000d3cd  mov     rdx, r10; hFileMappingObject
0x18000d3d0  mov     [rsp+88h+hSourceHandle], rax; hSourceHandle
0x18000d3d5  mov     rcx, r11; this
0x18000d3d8  mov     eax, [rbx+38h]
0x18000d3db  mov     [rsp+88h+var_48], eax; unsigned int
0x18000d3df  mov     rax, [rbx+30h]
0x18000d3e3  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x18000d3e8  mov     rax, [rbx+28h]
0x18000d3ec  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18000d3f1  mov     rax, [rbx+20h]
0x18000d3f5  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18000d3fa  mov     [rsp+88h+var_68], r14; LPHANDLE
0x18000d3ff  call    ?CopyTheme@CThemeServer@@QEAAJPEAXPEAPEAX01PEBG22KK00@Z; CThemeServer::CopyTheme(void *,void * *,void *,void * *,ushort const *,ushort const *,ushort const *,ulong,ulong,void *,void *)
0x18000d404  and     eax, 0EFFFFFFFh
0x18000d409  mov     [rbx+50h], eax
0x18000d40c  jl      short loc_18000D41B
0x18000d40e  mov     rcx, [rbx+40h]
0x18000d412  mov     [rdi], rcx
0x18000d415  mov     rcx, [r14]
0x18000d418  mov     [rsi], rcx
0x18000d41b  add     rsp, 60h
0x18000d41f  pop     r15
0x18000d421  pop     r14
0x18000d423  pop     rdi
0x18000d424  pop     rsi
0x18000d425  pop     rbx
0x18000d426  retn
```
