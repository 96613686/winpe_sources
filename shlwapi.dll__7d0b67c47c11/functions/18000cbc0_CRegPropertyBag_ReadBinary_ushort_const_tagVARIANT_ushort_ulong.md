# CRegPropertyBag::_ReadBinary(ushort const *,tagVARIANT *,ushort,ulong)

- ea: `0x18000cbc0`
- end: `0x18000cce4`
- name: `?_ReadBinary@CRegPropertyBag@@AEAAJPEBGPEAUtagVARIANT@@GK@Z`
- size: `292`
- prototype: `int(CRegPropertyBag *__hidden this, const unsigned __int16 *, struct tagVARIANT *, unsigned __int16, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006320`

## callees

- `0x18000cbc0`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cc1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cc1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccb9`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000cc56`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18000cc56`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18000cc99`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18000cc99`

## pseudocode

```c
__int64 __fastcall CRegPropertyBag::_ReadBinary(
        CRegPropertyBag *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3,
        __int16 a4,
        SIZE_T uBytes)
{
  signed int v8; // ebx
  BYTE *pvData; // rdi
  HKEY v10; // rcx
  LSTATUS v11; // eax
  __int64 v12; // rax
  IStream *v13; // rax
  DWORD pdwType; // [rsp+30h] [rbp-48h] BYREF

  v8 = -2147467259;
  if ( (!a4 || a4 == 13) && (unsigned int)uBytes >= 0x10 )
  {
    pvData = (BYTE *)LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( pvData )
    {
      v10 = (HKEY)*((_QWORD *)this + 4);
      pdwType = 0;
      v11 = SHGetValueW(v10, 0, a2, &pdwType, pvData, (DWORD *)&uBytes);
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      if ( v8 >= 0 )
      {
        v12 = *(_QWORD *)&GUID_NULL.Data1 - *(_QWORD *)pvData;
        if ( *(_QWORD *)&GUID_NULL.Data1 == *(_QWORD *)pvData )
          v12 = *(_QWORD *)GUID_NULL.Data4 - *((_QWORD *)pvData + 1);
        if ( !v12 )
        {
          v13 = SHCreateMemStream(pvData + 16, (int)uBytes - 16);
          a3->llVal = (LONGLONG)v13;
          if ( v13 )
          {
            a3->vt = 13;
            v8 = 0;
          }
          else
          {
            v8 = -2147024882;
          }
        }
      }
      LocalFree(pvData);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000cbc0  push    rbx
0x18000cbc2  push    rbp
0x18000cbc3  push    rsi
0x18000cbc4  push    rdi
0x18000cbc5  push    r12
0x18000cbc7  push    r14
0x18000cbc9  push    r15
0x18000cbcb  sub     rsp, 40h
0x18000cbcf  mov     rax, cs:__security_cookie
0x18000cbd6  xor     rax, rsp
0x18000cbd9  mov     [rsp+78h+var_40], rax
0x18000cbde  xor     r15d, r15d
0x18000cbe1  mov     rsi, r8
0x18000cbe4  mov     r14, rdx
0x18000cbe7  mov     rbp, rcx
0x18000cbea  mov     ebx, 80004005h
0x18000cbef  mov     r12d, 0Dh
0x18000cbf5  test    r9w, r9w
0x18000cbf9  jz      short loc_18000CC05
0x18000cbfb  cmp     r9w, r12w
0x18000cbff  jnz     loc_18000CCC6
0x18000cc05  cmp     dword ptr [rsp+78h+uBytes], 10h
0x18000cc0d  jb      loc_18000CCC6
0x18000cc13  mov     edx, dword ptr [rsp+78h+uBytes]; uBytes
0x18000cc1a  mov     ecx, 40h ; '@'; uFlags
0x18000cc1f  call    cs:__imp_LocalAlloc
0x18000cc25  mov     rdi, rax
0x18000cc28  test    rax, rax
0x18000cc2b  jz      loc_18000CCC1
0x18000cc31  mov     rcx, [rbp+20h]; hkey
0x18000cc35  lea     rax, [rsp+78h+uBytes]
0x18000cc3d  mov     [rsp+78h+pcbData], rax; pcbData
0x18000cc42  lea     r9, [rsp+78h+pdwType]; pdwType
0x18000cc47  mov     r8, r14; pszValue
0x18000cc4a  mov     [rsp+78h+pvData], rdi; pvData
0x18000cc4f  xor     edx, edx; pszSubKey
0x18000cc51  mov     [rsp+78h+pdwType], r15d
0x18000cc56  call    cs:__imp_SHGetValueW
0x18000cc5c  mov     ebx, eax
0x18000cc5e  test    eax, eax
0x18000cc60  jle     short loc_18000CC6B
0x18000cc62  movzx   ebx, ax
0x18000cc65  or      ebx, 80070000h
0x18000cc6b  test    ebx, ebx
0x18000cc6d  js      short loc_18000CCB6
0x18000cc6f  mov     rax, qword ptr cs:GUID_NULL.Data1
0x18000cc76  sub     rax, [rdi]
0x18000cc79  jnz     short loc_18000CC86
0x18000cc7b  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18000cc82  sub     rax, [rdi+8]
0x18000cc86  test    rax, rax
0x18000cc89  jnz     short loc_18000CCB6
0x18000cc8b  mov     edx, dword ptr [rsp+78h+uBytes]
0x18000cc92  lea     rcx, [rdi+10h]; pInit
0x18000cc96  add     edx, 0FFFFFFF0h; cbInit
0x18000cc99  call    cs:__imp_SHCreateMemStream
0x18000cc9f  mov     [rsi+8], rax
0x18000cca3  test    rax, rax
0x18000cca6  jz      short loc_18000CCB1
0x18000cca8  mov     [rsi], r12w
0x18000ccac  mov     ebx, r15d
0x18000ccaf  jmp     short loc_18000CCB6
0x18000ccb1  mov     ebx, 8007000Eh
0x18000ccb6  mov     rcx, rdi; hMem
0x18000ccb9  call    cs:__imp_LocalFree
0x18000ccbf  jmp     short loc_18000CCC6
0x18000ccc1  mov     ebx, 8007000Eh
0x18000ccc6  mov     eax, ebx
0x18000ccc8  mov     rcx, [rsp+78h+var_40]
0x18000cccd  xor     rcx, rsp; StackCookie
0x18000ccd0  call    __security_check_cookie
0x18000ccd5  add     rsp, 40h
0x18000ccd9  pop     r15
0x18000ccdb  pop     r14
0x18000ccdd  pop     r12
0x18000ccdf  pop     rdi
0x18000cce0  pop     rsi
0x18000cce1  pop     rbp
0x18000cce2  pop     rbx
0x18000cce3  retn
```
