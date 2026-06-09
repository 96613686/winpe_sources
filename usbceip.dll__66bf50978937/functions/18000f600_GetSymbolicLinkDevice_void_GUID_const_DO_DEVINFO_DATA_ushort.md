# GetSymbolicLinkDevice(void *,_GUID const *,_DO_DEVINFO_DATA *,ushort * *)

- ea: `0x18000f600`
- end: `0x18000f743`
- name: `?GetSymbolicLinkDevice@@YAKPEAXPEBU_GUID@@PEAU_DO_DEVINFO_DATA@@PEAPEAG@Z`
- size: `323`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, struct _DO_DEVINFO_DATA *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18000f74c`

## callees

- `0x180002410`
- `0x180002e4a`
- `0x180002e56`
- `0x18000f600`
- `0x18000fea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6ce`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000f661`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000f661`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000f6c4`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000f6c4`

## pseudocode

```c
__int64 __fastcall GetSymbolicLinkDevice(
        void *a1,
        const struct _GUID *a2,
        struct _DO_DEVINFO_DATA *a3,
        unsigned __int16 **a4)
{
  _DWORD *v6; // rdi
  DWORD LastError; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  _DWORD *v10; // rax
  size_t v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned int i; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v15[2]; // [rsp+38h] [rbp-40h] BYREF

  *a4 = 0;
  i = 0;
  memset(v15, 0, sizeof(v15));
  LODWORD(v15[0]) = 32;
  v6 = 0;
  if ( (unsigned int)DevObjEnumDeviceInterfaces(a1, a3, &GUID_DEVINTERFACE_USB_HUB, 0, v15) )
  {
    v8 = 0;
    v9 = 0;
    for ( i = 0; ; v9 = i )
    {
      if ( v9 != v8 )
      {
        v8 = v9;
        free(v6);
        v10 = o_malloc_0(v8);
        v6 = v10;
        if ( !v10 )
          goto LABEL_10;
        *v10 = 8;
      }
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(a1, v15, v6, v8, &i, 0) )
        break;
      if ( GetLastError() != 122 )
        goto LABEL_2;
    }
    v11 = i - 4;
    v12 = (unsigned __int16 *)o_malloc_0(v11);
    *a4 = v12;
    if ( !v12 )
    {
LABEL_10:
      LastError = 14;
      goto LABEL_13;
    }
    memcpy_0(v12, v6 + 1, (unsigned int)v11);
    (*a4)[(v11 >> 1) - 1] = 0;
    LastError = 0;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
LABEL_13:
  free(v6);
  return LastError;
}

```

## disassembly

```asm
0x18000f600  mov     [rsp+arg_8], rbx
0x18000f605  push    rbp
0x18000f606  push    rsi
0x18000f607  push    rdi
0x18000f608  sub     rsp, 60h
0x18000f60c  mov     rax, cs:__security_cookie
0x18000f613  xor     rax, rsp
0x18000f616  mov     [rsp+78h+var_20], rax
0x18000f61b  mov     rbp, rcx
0x18000f61e  mov     qword ptr [r9], 0
0x18000f625  xorps   xmm0, xmm0
0x18000f628  mov     [rsp+78h+var_48], 0
0x18000f630  lea     rcx, [rsp+78h+var_40]
0x18000f635  mov     rsi, r9
0x18000f638  mov     [rsp+78h+var_58], rcx
0x18000f63d  mov     rdx, r8
0x18000f640  movups  [rsp+78h+var_40], xmm0
0x18000f645  mov     rcx, rbp
0x18000f648  mov     dword ptr [rsp+78h+var_40], 20h ; ' '
0x18000f650  xor     r9d, r9d
0x18000f653  lea     r8, GUID_DEVINTERFACE_USB_HUB
0x18000f65a  movups  [rsp+78h+var_30], xmm0
0x18000f65f  xor     edi, edi
0x18000f661  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18000f667  test    eax, eax
0x18000f669  jnz     short loc_18000F678
0x18000f66b  call    cs:__imp_GetLastError
0x18000f671  mov     ebx, eax
0x18000f673  jmp     loc_18000F71C
0x18000f678  xor     ebx, ebx
0x18000f67a  xor     eax, eax
0x18000f67c  mov     [rsp+78h+var_48], eax
0x18000f680  cmp     eax, ebx
0x18000f682  jz      short loc_18000F6A3
0x18000f684  mov     rcx, rdi; Block
0x18000f687  mov     ebx, eax
0x18000f689  call    free
0x18000f68e  mov     ecx, ebx; Size
0x18000f690  call    _o_malloc_0
0x18000f695  mov     rdi, rax
0x18000f698  test    rax, rax
0x18000f69b  jz      short loc_18000F6DF
0x18000f69d  mov     dword ptr [rax], 8
0x18000f6a3  lea     rax, [rsp+78h+var_48]
0x18000f6a8  mov     [rsp+78h+var_50], 0
0x18000f6b1  mov     r9d, ebx
0x18000f6b4  mov     [rsp+78h+var_58], rax
0x18000f6b9  mov     r8, rdi
0x18000f6bc  lea     rdx, [rsp+78h+var_40]
0x18000f6c1  mov     rcx, rbp
0x18000f6c4  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18000f6ca  test    eax, eax
0x18000f6cc  jnz     short loc_18000F6E6
0x18000f6ce  call    cs:__imp_GetLastError
0x18000f6d4  cmp     eax, 7Ah ; 'z'
0x18000f6d7  jnz     short loc_18000F66B
0x18000f6d9  mov     eax, [rsp+78h+var_48]
0x18000f6dd  jmp     short loc_18000F680
0x18000f6df  mov     ebx, 0Eh
0x18000f6e4  jmp     short loc_18000F71C
0x18000f6e6  mov     eax, [rsp+78h+var_48]
0x18000f6ea  add     eax, 0FFFFFFFCh
0x18000f6ed  mov     ecx, eax; Size
0x18000f6ef  mov     ebx, eax
0x18000f6f1  call    _o_malloc_0
0x18000f6f6  mov     [rsi], rax
0x18000f6f9  test    rax, rax
0x18000f6fc  jz      short loc_18000F6DF
0x18000f6fe  lea     rdx, [rdi+4]; Src
0x18000f702  mov     r8d, ebx; Size
0x18000f705  mov     rcx, rax; void *
0x18000f708  call    memcpy_0
0x18000f70d  mov     rcx, [rsi]
0x18000f710  xor     eax, eax
0x18000f712  shr     rbx, 1
0x18000f715  mov     [rcx+rbx*2-2], ax
0x18000f71a  xor     ebx, ebx
0x18000f71c  mov     rcx, rdi; Block
0x18000f71f  call    free
0x18000f724  mov     eax, ebx
0x18000f726  mov     rcx, [rsp+78h+var_20]
0x18000f72b  xor     rcx, rsp; StackCookie
0x18000f72e  call    __security_check_cookie
0x18000f733  mov     rbx, [rsp+78h+arg_8]
0x18000f73b  add     rsp, 60h
0x18000f73f  pop     rdi
0x18000f740  pop     rsi
0x18000f741  pop     rbp
0x18000f742  retn
```
