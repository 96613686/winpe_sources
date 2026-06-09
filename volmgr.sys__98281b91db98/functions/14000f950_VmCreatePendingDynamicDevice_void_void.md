# VmCreatePendingDynamicDevice(void *,void *)

- ea: `0x14000f950`
- end: `0x14000fa53`
- name: `?VmCreatePendingDynamicDevice@@YAJPEAX0@Z`
- size: `259`
- prototype: `__int64 __fastcall(struct VM_ROOT_EXTENSION *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005050`
- `0x140005090`
- `0x14000f950`
- `0x140010898`
- `0x14001171c`

## pseudocode

```c
__int64 __fastcall VmCreatePendingDynamicDevice(struct VM_ROOT_EXTENSION *a1, void *a2)
{
  __int64 v2; // rsi
  __int64 v5; // rax
  __int64 result; // rax
  struct VM_ROOT_EXTENSION **v7; // r8
  struct VM_ROOT_EXTENSION *v8; // rcx
  struct _DEVICE_OBJECT *v9; // [rsp+40h] [rbp-28h] BYREF
  struct _GUID v10; // [rsp+48h] [rbp-20h] BYREF

  v2 = *((_QWORD *)a1 + 49);
  v9 = 0;
  v10 = 0;
  (*(void (__fastcall **)(void *, struct _GUID *))(v2 + 120))(a2, &v10);
  if ( *((_QWORD *)a1 + 45) )
    VmpCheckForRevertGptAttributes(a1, 1, 0, &v10, 0, 0, a2, 0);
  v5 = (*(__int64 (__fastcall **)(void *))(v2 + 152))(a2);
  result = VmpCreateDynamicDevice(a2, (struct _DEVICE_OBJECT *)&v10, v5, &v9);
  if ( (int)result >= 0 )
  {
    v7 = (struct VM_ROOT_EXTENSION **)*((_QWORD *)a1 + 31);
    if ( *v7 != (struct VM_ROOT_EXTENSION *)((char *)a1 + 240) )
      __fastfail(3u);
    v8 = (struct VM_ROOT_EXTENSION *)((char *)v9->DeviceExtension + 32);
    result = 0;
    *((_QWORD *)v8 + 1) = v7;
    *(_QWORD *)v8 = (char *)a1 + 240;
    *v7 = v8;
    *((_QWORD *)a1 + 31) = v8;
  }
  return result;
}

```

## disassembly

```asm
0x14000f950  mov     r11, rsp
0x14000f953  mov     [r11+18h], rbx
0x14000f957  mov     [r11+20h], rsi
0x14000f95b  push    rdi
0x14000f95c  sub     rsp, 60h
0x14000f960  mov     rax, cs:__security_cookie
0x14000f967  xor     rax, rsp
0x14000f96a  mov     [rsp+68h+var_10], rax
0x14000f96f  mov     rsi, [rcx+188h]
0x14000f976  mov     rdi, rdx
0x14000f979  xorps   xmm0, xmm0
0x14000f97c  mov     qword ptr [r11-28h], 0
0x14000f984  mov     rbx, rcx
0x14000f987  lea     rdx, [r11-20h]
0x14000f98b  movups  xmmword ptr [rsp+68h+var_20.Data1], xmm0
0x14000f990  mov     rax, [rsi+78h]
0x14000f994  mov     rcx, rdi
0x14000f997  call    _guard_dispatch_icall
0x14000f99c  cmp     qword ptr [rbx+168h], 0
0x14000f9a4  jz      short loc_14000F9D7
0x14000f9a6  mov     [rsp+68h+var_30], 0; struct _DEVICE_OBJECT *
0x14000f9af  lea     r9, [rsp+68h+var_20]; struct _GUID *
0x14000f9b4  mov     [rsp+68h+var_38], rdi; void *
0x14000f9b9  xor     r8d, r8d; unsigned __int8
0x14000f9bc  mov     [rsp+68h+var_40], 0; unsigned int
0x14000f9c4  mov     dl, 1; unsigned __int8
0x14000f9c6  mov     rcx, rbx; struct VM_ROOT_EXTENSION *
0x14000f9c9  mov     [rsp+68h+var_48], 0; struct _GUID *
0x14000f9d2  call    ?VmpCheckForRevertGptAttributes@@YAXPEAVVM_ROOT_EXTENSION@@EEPEAU_GUID@@1KPEAXPEAU_DEVICE_OBJECT@@@Z; VmpCheckForRevertGptAttributes(VM_ROOT_EXTENSION *,uchar,uchar,_GUID *,_GUID *,ulong,void *,_DEVICE_OBJECT *)
0x14000f9d7  mov     rax, [rsi+98h]
0x14000f9de  mov     rcx, rdi
0x14000f9e1  call    _guard_dispatch_icall
0x14000f9e6  lea     r9, [rsp+68h+var_28]; struct _DEVICE_OBJECT **
0x14000f9eb  mov     r8, rax; unsigned __int64
0x14000f9ee  lea     rdx, [rsp+68h+var_20]; struct _GUID *
0x14000f9f3  mov     rcx, rdi; void *
0x14000f9f6  call    ?VmpCreateDynamicDevice@@YAJPEAXPEAU_GUID@@_KPEAPEAU_DEVICE_OBJECT@@@Z; VmpCreateDynamicDevice(void *,_GUID *,unsigned __int64,_DEVICE_OBJECT * *)
0x14000f9fb  test    eax, eax
0x14000f9fd  js      short loc_14000FA33
0x14000f9ff  lea     rdx, [rbx+0F0h]
0x14000fa06  mov     r8, [rdx+8]
0x14000fa0a  cmp     [r8], rdx
0x14000fa0d  jz      short loc_14000FA16
0x14000fa0f  mov     ecx, 3
0x14000fa14  int     29h; Win8: RtlFailFast(ecx)
0x14000fa16  mov     rax, [rsp+68h+var_28]
0x14000fa1b  mov     rcx, [rax+40h]
0x14000fa1f  add     rcx, 20h ; ' '
0x14000fa23  xor     eax, eax
0x14000fa25  mov     [rcx+8], r8
0x14000fa29  mov     [rcx], rdx
0x14000fa2c  mov     [r8], rcx
0x14000fa2f  mov     [rdx+8], rcx
0x14000fa33  mov     rcx, [rsp+68h+var_10]
0x14000fa38  xor     rcx, rsp; StackCookie
0x14000fa3b  call    __security_check_cookie
0x14000fa40  lea     r11, [rsp+68h+var_8]
0x14000fa45  mov     rbx, [r11+20h]
0x14000fa49  mov     rsi, [r11+28h]
0x14000fa4d  mov     rsp, r11
0x14000fa50  pop     rdi
0x14000fa51  retn
```
