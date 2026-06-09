# PnPHelper::_GetDeviceInstanceFromDevNode(ushort const *,ulong *,ulong *)

- ea: `0x18002b9d8`
- end: `0x18002bae5`
- name: `?_GetDeviceInstanceFromDevNode@PnPHelper@@YAJPEBGPEAK1@Z`
- size: `269`
- prototype: `__int64 __fastcall(PnPHelper *this, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002df88`

## callees

- `0x18002b9d8`
- `0x180032c90`

## import_xrefs

- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002bab9`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002bab9`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18002ba6b`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18002ba6b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002bac2`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18002bac2`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002ba16`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002ba16`

## pseudocode

```c
__int64 __fastcall PnPHelper::_GetDeviceInstanceFromDevNode(
        PnPHelper *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  unsigned int v7; // esi
  __int64 DeviceInfoList; // rax
  __int64 v9; // rbx
  int v11; // [rsp+40h] [rbp-68h] BYREF
  int v12; // [rsp+44h] [rbp-64h] BYREF
  __int128 v13; // [rsp+48h] [rbp-60h] BYREF
  __int128 v14; // [rsp+58h] [rbp-50h]
  __int128 v15; // [rsp+68h] [rbp-40h]

  v7 = -2147467259;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  *(_DWORD *)a2 = 0;
  v9 = DeviceInfoList;
  if ( a3 )
    *a3 = 0;
  if ( DeviceInfoList != -1 )
  {
    v13 = 0;
    LODWORD(v13) = 48;
    v14 = 0;
    v15 = 0;
    if ( (unsigned int)DevObjOpenDeviceInfo(DeviceInfoList, this, 0, 0, &v13) )
    {
      v7 = 0;
      *(_DWORD *)a2 = DWORD1(v14);
      v12 = 7;
      v11 = 0;
      ((void (__fastcall *)(__int64, __int128 *, const DEVPROPKEY *, int *, unsigned int *, int, int *, _DWORD))DevObjGetDeviceProperty)(
        v9,
        &v13,
        &DEVPKEY_Device_SessionId,
        &v12,
        a3,
        4,
        &v11,
        0);
    }
    DevObjDestroyDeviceInfoList(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18002b9d8  push    rbx
0x18002b9da  push    rbp
0x18002b9db  push    rsi
0x18002b9dc  push    rdi
0x18002b9dd  push    r14
0x18002b9df  sub     rsp, 80h
0x18002b9e6  mov     rax, cs:__security_cookie
0x18002b9ed  xor     rax, rsp
0x18002b9f0  mov     [rsp+0A8h+var_30], rax
0x18002b9f5  mov     rdi, r8
0x18002b9f8  mov     [rsp+0A8h+var_88], 0
0x18002ba01  mov     r14, rdx
0x18002ba04  mov     rbp, rcx
0x18002ba07  xor     r8d, r8d
0x18002ba0a  xor     edx, edx
0x18002ba0c  xor     ecx, ecx
0x18002ba0e  xor     r9d, r9d
0x18002ba11  mov     esi, 80004005h
0x18002ba16  call    cs:__imp_DevObjCreateDeviceInfoList
0x18002ba1c  mov     dword ptr [r14], 0
0x18002ba23  mov     rbx, rax
0x18002ba26  test    rdi, rdi
0x18002ba29  jz      short loc_18002BA31
0x18002ba2b  mov     dword ptr [rdi], 0
0x18002ba31  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002ba35  jz      loc_18002BAC8
0x18002ba3b  xorps   xmm0, xmm0
0x18002ba3e  lea     rax, [rsp+0A8h+var_60]
0x18002ba43  movups  [rsp+0A8h+var_60], xmm0
0x18002ba48  xor     r9d, r9d
0x18002ba4b  mov     dword ptr [rsp+0A8h+var_60], 30h ; '0'
0x18002ba53  xor     r8d, r8d
0x18002ba56  mov     [rsp+0A8h+var_88], rax
0x18002ba5b  mov     rdx, rbp
0x18002ba5e  mov     rcx, rbx
0x18002ba61  movups  [rsp+0A8h+var_50], xmm0
0x18002ba66  movups  [rsp+0A8h+var_40], xmm0
0x18002ba6b  call    cs:__imp_DevObjOpenDeviceInfo
0x18002ba71  test    eax, eax
0x18002ba73  jz      short loc_18002BABF
0x18002ba75  mov     eax, dword ptr [rsp+0A8h+var_50+4]
0x18002ba79  lea     r9, [rsp+0A8h+var_64]
0x18002ba7e  xor     esi, esi
0x18002ba80  mov     [r14], eax
0x18002ba83  mov     [rsp+0A8h+var_70], esi
0x18002ba87  lea     rax, [rsp+0A8h+var_68]
0x18002ba8c  mov     [rsp+0A8h+var_78], rax
0x18002ba91  lea     r8, DEVPKEY_Device_SessionId
0x18002ba98  mov     [rsp+0A8h+var_80], 4
0x18002baa0  lea     rdx, [rsp+0A8h+var_60]
0x18002baa5  mov     rcx, rbx
0x18002baa8  mov     [rsp+0A8h+var_88], rdi
0x18002baad  mov     [rsp+0A8h+var_64], 7
0x18002bab5  mov     [rsp+0A8h+var_68], esi
0x18002bab9  call    cs:__imp_DevObjGetDeviceProperty
0x18002babf  mov     rcx, rbx
0x18002bac2  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002bac8  mov     eax, esi
0x18002baca  mov     rcx, [rsp+0A8h+var_30]
0x18002bacf  xor     rcx, rsp; StackCookie
0x18002bad2  call    __security_check_cookie
0x18002bad7  add     rsp, 80h
0x18002bade  pop     r14
0x18002bae0  pop     rdi
0x18002bae1  pop     rsi
0x18002bae2  pop     rbp
0x18002bae3  pop     rbx
0x18002bae4  retn
```
