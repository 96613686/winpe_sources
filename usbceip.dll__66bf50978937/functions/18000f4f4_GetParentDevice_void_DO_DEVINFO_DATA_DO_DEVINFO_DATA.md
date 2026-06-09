# GetParentDevice(void *,_DO_DEVINFO_DATA *,_DO_DEVINFO_DATA *)

- ea: `0x18000f4f4`
- end: `0x18000f58e`
- name: `?GetParentDevice@@YAKPEAXPEAU_DO_DEVINFO_DATA@@1@Z`
- size: `154`
- prototype: `__int64 __fastcall(void *, struct _DO_DEVINFO_DATA *, struct _DEVPROPKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f74c`

## callees

- `0x180002e4a`
- `0x18000f410`
- `0x18000f4f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f573`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000f569`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000f569`

## pseudocode

```c
__int64 __fastcall GetParentDevice(void *a1, struct _DO_DEVINFO_DATA *a2, struct _DEVPROPKEY *a3)
{
  unsigned int DeviceProperty; // eax
  void *v6; // rdi
  DWORD LastError; // ebx
  unsigned int v9; // [rsp+30h] [rbp-38h] BYREF
  void *Block; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+88h] [rbp+20h] BYREF

  v11 = 0;
  v9 = 0;
  Block = 0;
  DeviceProperty = GetDeviceProperty(a1, a2, a3, &v9, &v11, (unsigned __int8 **)&Block);
  v6 = Block;
  LastError = DeviceProperty;
  if ( !DeviceProperty )
  {
    *((_WORD *)Block + ((unsigned __int64)v11 >> 1) - 1) = 0;
    a3->fmtid.Data1 = 48;
    if ( !(unsigned int)DevObjOpenDeviceInfo(a1, v6, 0, 0, a3) )
      LastError = GetLastError();
  }
  free(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000f4f4  mov     r11, rsp
0x18000f4f7  push    rbx
0x18000f4f8  push    rbp
0x18000f4f9  push    rsi
0x18000f4fa  push    rdi
0x18000f4fb  sub     rsp, 48h
0x18000f4ff  lea     rax, [r11-30h]
0x18000f503  mov     dword ptr [r11+20h], 0
0x18000f50b  mov     [r11-40h], rax
0x18000f50f  lea     r9, [r11-38h]; unsigned int *
0x18000f513  lea     rax, [r11+20h]
0x18000f517  mov     [rsp+68h+var_38], 0
0x18000f51f  mov     [r11-48h], rax
0x18000f523  mov     rsi, r8
0x18000f526  mov     rbp, rcx
0x18000f529  mov     qword ptr [r11-30h], 0
0x18000f531  call    ?GetDeviceProperty@@YAKPEAXPEAU_DO_DEVINFO_DATA@@AEBU_DEVPROPKEY@@PEAK3PEAPEAE@Z; GetDeviceProperty(void *,_DO_DEVINFO_DATA *,_DEVPROPKEY const &,ulong *,ulong *,uchar * *)
0x18000f536  mov     rdi, [rsp+68h+Block]
0x18000f53b  mov     ebx, eax
0x18000f53d  test    eax, eax
0x18000f53f  jnz     short loc_18000F57B
0x18000f541  mov     edx, [rsp+68h+arg_18]
0x18000f548  xor     ecx, ecx
0x18000f54a  shr     rdx, 1
0x18000f54d  xor     r9d, r9d
0x18000f550  xor     r8d, r8d
0x18000f553  mov     [rsp+68h+var_48], rsi
0x18000f558  mov     [rdi+rdx*2-2], cx
0x18000f55d  mov     rdx, rdi
0x18000f560  mov     rcx, rbp
0x18000f563  mov     dword ptr [rsi], 30h ; '0'
0x18000f569  call    cs:__imp_DevObjOpenDeviceInfo
0x18000f56f  test    eax, eax
0x18000f571  jnz     short loc_18000F57B
0x18000f573  call    cs:__imp_GetLastError
0x18000f579  mov     ebx, eax
0x18000f57b  mov     rcx, rdi; Block
0x18000f57e  call    free
0x18000f583  mov     eax, ebx
0x18000f585  add     rsp, 48h
0x18000f589  pop     rdi
0x18000f58a  pop     rsi
0x18000f58b  pop     rbp
0x18000f58c  pop     rbx
0x18000f58d  retn
```
