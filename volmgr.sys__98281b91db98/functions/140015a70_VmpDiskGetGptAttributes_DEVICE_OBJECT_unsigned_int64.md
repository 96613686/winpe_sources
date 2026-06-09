# VmpDiskGetGptAttributes(_DEVICE_OBJECT *,unsigned __int64 *)

- ea: `0x140015a70`
- end: `0x140015ad9`
- name: `?VmpDiskGetGptAttributes@@YAJPEAU_DEVICE_OBJECT@@PEA_K@Z`
- size: `105`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f3b0`
- `0x140010d7c`
- `0x140013e00`
- `0x140015900`

## callees

- `0x140002db0`
- `0x140005050`
- `0x140015a70`

## pseudocode

```c
NTSTATUS __fastcall VmpDiskGetGptAttributes(struct _DEVICE_OBJECT *a1, unsigned __int64 *a2)
{
  NTSTATUS result; // eax
  __int128 v4; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v4 = 0;
  result = VmpSendDeviceControl(a1, 0x700E8u, 0, 0, &v4, 0x10u);
  if ( result >= 0 )
    *a2 = *((_QWORD *)&v4 + 1);
  return result;
}

```

## disassembly

```asm
0x140015a70  push    rbx
0x140015a72  sub     rsp, 50h
0x140015a76  mov     rax, cs:__security_cookie
0x140015a7d  xor     rax, rsp
0x140015a80  mov     [rsp+58h+var_18], rax
0x140015a85  mov     rbx, rdx
0x140015a88  mov     qword ptr [rdx], 0
0x140015a8f  xorps   xmm0, xmm0
0x140015a92  mov     [rsp+58h+var_30], 10h; ULONG
0x140015a9a  lea     rax, [rsp+58h+var_28]
0x140015a9f  mov     edx, 700E8h; IoControlCode
0x140015aa4  xor     r9d, r9d; InputBufferLength
0x140015aa7  mov     [rsp+58h+var_38], rax; PVOID
0x140015aac  xor     r8d, r8d; InputBuffer
0x140015aaf  movups  [rsp+58h+var_28], xmm0
0x140015ab4  call    VmpSendDeviceControl
0x140015ab9  test    eax, eax
0x140015abb  js      short loc_140015AC5
0x140015abd  mov     rcx, qword ptr [rsp+58h+var_28+8]
0x140015ac2  mov     [rbx], rcx
0x140015ac5  mov     rcx, [rsp+58h+var_18]
0x140015aca  xor     rcx, rsp; StackCookie
0x140015acd  call    __security_check_cookie
0x140015ad2  add     rsp, 50h
0x140015ad6  pop     rbx
0x140015ad7  retn
```
