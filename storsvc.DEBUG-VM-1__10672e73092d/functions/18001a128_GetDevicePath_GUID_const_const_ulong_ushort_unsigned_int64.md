# GetDevicePath(_GUID const * const,ulong,ushort *,unsigned __int64)

- ea: `0x18001a128`
- end: `0x18001a2a3`
- name: `?GetDevicePath@@YAJQEBU_GUID@@KPEAG_K@Z`
- size: `379`
- prototype: `int(const struct _GUID *const, unsigned int, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001af64`

## callees

- `0x18000d030`
- `0x180012c9c`
- `0x18001a128`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a210`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a210`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a275`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a275`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001a1d9`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001a1d9`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001a204`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001a24e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001a204`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18001a24e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001a27e`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001a27e`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001a1ae`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001a1ae`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001a170`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001a170`

## pseudocode

```c
__int64 __fastcall GetDevicePath(const struct _GUID *const a1, unsigned int a2, unsigned __int16 *a3)
{
  __int64 DeviceInfoList; // rax
  __int64 v6; // rsi
  unsigned int v7; // ebx
  wchar_t *v8; // rax
  wchar_t *v9; // rdi
  SIZE_T uBytes; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v12[2]; // [rsp+38h] [rbp-40h] BYREF

  LODWORD(uBytes) = 0;
  memset(v12, 0, sizeof(v12));
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v6 = DeviceInfoList;
  if ( DeviceInfoList != -1
    && (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_SD_HOST_CONTROLLER, 0, 18, 0, 0)
    && (LODWORD(v12[0]) = 32, (unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_SD_HOST_CONTROLLER, a2, v12)) )
  {
    DevObjGetDeviceInterfaceDetail(v6, v12, 0, 0, &uBytes, 0);
    v8 = (wchar_t *)LocalAlloc(0, (unsigned int)uBytes);
    v9 = v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = 8;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v12, v8, (unsigned int)uBytes, &uBytes, 0) )
        v7 = StringCchCopyW(a3, 0x104u, v9 + 2);
      else
        v7 = -2147467259;
      LocalFree(v9);
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    v7 = -2147467259;
  }
  DevObjDestroyDeviceInfoList(v6);
  return v7;
}

```

## disassembly

```asm
0x18001a128  mov     [rsp+arg_0], rbx
0x18001a12d  push    rbp
0x18001a12e  push    rsi
0x18001a12f  push    rdi
0x18001a130  sub     rsp, 60h
0x18001a134  mov     rax, cs:__security_cookie
0x18001a13b  xor     rax, rsp
0x18001a13e  mov     [rsp+78h+var_20], rax
0x18001a143  xorps   xmm0, xmm0
0x18001a146  mov     dword ptr [rsp+78h+uBytes], 0
0x18001a14e  mov     rbp, r8
0x18001a151  mov     [rsp+78h+var_58], 0
0x18001a15a  mov     ebx, edx
0x18001a15c  xor     r8d, r8d
0x18001a15f  xor     edx, edx
0x18001a161  xor     r9d, r9d
0x18001a164  xor     ecx, ecx
0x18001a166  movups  [rsp+78h+var_40], xmm0
0x18001a16b  movups  [rsp+78h+var_30], xmm0
0x18001a170  call    cs:__imp_DevObjCreateDeviceInfoList
0x18001a176  mov     rsi, rax
0x18001a179  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a17d  jnz     short loc_18001A189
0x18001a17f  mov     ebx, 80004005h
0x18001a184  jmp     loc_18001A27B
0x18001a189  mov     [rsp+78h+var_50], 0
0x18001a192  lea     rdx, GUID_SD_HOST_CONTROLLER
0x18001a199  mov     r9d, 12h
0x18001a19f  mov     [rsp+78h+var_58], 0
0x18001a1a8  xor     r8d, r8d
0x18001a1ab  mov     rcx, rsi
0x18001a1ae  call    cs:__imp_DevObjGetClassDevs
0x18001a1b4  test    eax, eax
0x18001a1b6  jz      short loc_18001A17F
0x18001a1b8  lea     rax, [rsp+78h+var_40]
0x18001a1bd  mov     dword ptr [rsp+78h+var_40], 20h ; ' '
0x18001a1c5  mov     r9d, ebx
0x18001a1c8  mov     [rsp+78h+var_58], rax
0x18001a1cd  lea     r8, GUID_SD_HOST_CONTROLLER
0x18001a1d4  xor     edx, edx
0x18001a1d6  mov     rcx, rsi
0x18001a1d9  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18001a1df  test    eax, eax
0x18001a1e1  jz      short loc_18001A17F
0x18001a1e3  lea     rax, [rsp+78h+uBytes]
0x18001a1e8  mov     [rsp+78h+var_50], 0
0x18001a1f1  xor     r9d, r9d
0x18001a1f4  mov     [rsp+78h+var_58], rax
0x18001a1f9  xor     r8d, r8d
0x18001a1fc  lea     rdx, [rsp+78h+var_40]
0x18001a201  mov     rcx, rsi
0x18001a204  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001a20a  mov     edx, dword ptr [rsp+78h+uBytes]; uBytes
0x18001a20e  xor     ecx, ecx; uFlags
0x18001a210  call    cs:__imp_LocalAlloc
0x18001a216  mov     rdi, rax
0x18001a219  test    rax, rax
0x18001a21c  jnz     short loc_18001A225
0x18001a21e  mov     ebx, 8007000Eh
0x18001a223  jmp     short loc_18001A27B
0x18001a225  mov     dword ptr [rax], 8
0x18001a22b  lea     rdx, [rsp+78h+var_40]
0x18001a230  mov     r9d, dword ptr [rsp+78h+uBytes]
0x18001a235  lea     rax, [rsp+78h+uBytes]
0x18001a23a  mov     [rsp+78h+var_50], 0
0x18001a243  mov     r8, rdi
0x18001a246  mov     rcx, rsi
0x18001a249  mov     [rsp+78h+var_58], rax
0x18001a24e  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18001a254  test    eax, eax
0x18001a256  jnz     short loc_18001A25F
0x18001a258  mov     ebx, 80004005h
0x18001a25d  jmp     short loc_18001A272
0x18001a25f  lea     r8, [rdi+4]; wchar_t *
0x18001a263  mov     edx, 104h; unsigned __int64
0x18001a268  mov     rcx, rbp; wchar_t *
0x18001a26b  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001a270  mov     ebx, eax
0x18001a272  mov     rcx, rdi; hMem
0x18001a275  call    cs:__imp_LocalFree
0x18001a27b  mov     rcx, rsi
0x18001a27e  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001a284  mov     eax, ebx
0x18001a286  mov     rcx, [rsp+78h+var_20]
0x18001a28b  xor     rcx, rsp; StackCookie
0x18001a28e  call    __security_check_cookie
0x18001a293  mov     rbx, [rsp+78h+arg_0]
0x18001a29b  add     rsp, 60h
0x18001a29f  pop     rdi
0x18001a2a0  pop     rsi
0x18001a2a1  pop     rbp
0x18001a2a2  retn
```
