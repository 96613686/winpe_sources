# RegReadValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)

- ea: `0x180010ed0`
- end: `0x180010fb1`
- name: `?RegReadValue@@YAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z`
- size: `225`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, DWORD dwFlags, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001384`
- `0x180010ed0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010f87`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010f87`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010f1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010f67`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010f1b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010f67`

## pseudocode

```c
__int64 __fastcall RegReadValue(HKEY hkey, LPCWSTR lpValue, DWORD dwFlags, unsigned __int8 **a4, unsigned int *a5)
{
  LSTATUS ValueW; // eax
  unsigned int v10; // ebx
  void *pvData; // rdi
  DWORD v12; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-48h] BYREF
  DWORD pdwType[17]; // [rsp+44h] [rbp-44h] BYREF

  pcbData = 0;
  pdwType[0] = 0;
  ValueW = RegGetValueW(hkey, 0, lpValue, dwFlags, pdwType, 0, &pcbData);
  v10 = ValueW;
  if ( ValueW )
  {
    pvData = 0;
  }
  else
  {
    pvData = operator new[](pcbData);
    if ( !pvData )
    {
      v10 = -2147024882;
LABEL_9:
      operator delete[](pvData);
      return v10;
    }
    ValueW = RegGetValueW(hkey, 0, lpValue, dwFlags, pdwType, pvData, &pcbData);
    v10 = ValueW;
    if ( !ValueW )
    {
      v10 = 0;
      v12 = pcbData;
      *a4 = (unsigned __int8 *)pvData;
      *a5 = v12;
      return v10;
    }
  }
  if ( ValueW > 0 )
    v10 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_9;
  return v10;
}

```

## disassembly

```asm
0x180010ed0  mov     r11, rsp
0x180010ed3  push    rbx
0x180010ed4  push    rbp
0x180010ed5  push    rsi
0x180010ed6  push    rdi
0x180010ed7  push    r14
0x180010ed9  push    r15
0x180010edb  sub     rsp, 58h
0x180010edf  lea     rax, [r11-48h]
0x180010ee3  mov     [rsp+88h+var_48], 0
0x180010eeb  mov     [r11-58h], rax
0x180010eef  mov     rsi, r9
0x180010ef2  mov     ebp, r8d
0x180010ef5  mov     qword ptr [r11-60h], 0
0x180010efd  mov     r9d, r8d; dwFlags
0x180010f00  mov     [rsp+88h+var_44], 0
0x180010f08  lea     rax, [r11-44h]
0x180010f0c  mov     r14, rdx
0x180010f0f  mov     r8, rdx; lpValue
0x180010f12  mov     [r11-68h], rax
0x180010f16  xor     edx, edx; lpSubKey
0x180010f18  mov     r15, rcx
0x180010f1b  call    cs:__imp_RegGetValueW
0x180010f21  mov     ebx, eax
0x180010f23  test    eax, eax
0x180010f25  jz      short loc_180010F2B
0x180010f27  xor     edi, edi
0x180010f29  jmp     short loc_180010F73
0x180010f2b  mov     ecx, [rsp+88h+var_48]; unsigned __int64
0x180010f2f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010f34  mov     rdi, rax
0x180010f37  test    rax, rax
0x180010f3a  jnz     short loc_180010F43
0x180010f3c  mov     ebx, 8007000Eh
0x180010f41  jmp     short loc_180010F84
0x180010f43  lea     rax, [rsp+88h+var_48]
0x180010f48  mov     r9d, ebp; dwFlags
0x180010f4b  mov     [rsp+88h+pcbData], rax; pcbData
0x180010f50  mov     r8, r14; lpValue
0x180010f53  lea     rax, [rsp+88h+var_44]
0x180010f58  mov     [rsp+88h+pvData], rdi; pvData
0x180010f5d  xor     edx, edx; lpSubKey
0x180010f5f  mov     [rsp+88h+pdwType], rax; pdwType
0x180010f64  mov     rcx, r15; hkey
0x180010f67  call    cs:__imp_RegGetValueW
0x180010f6d  mov     ebx, eax
0x180010f6f  test    eax, eax
0x180010f71  jz      short loc_180010F8F
0x180010f73  test    eax, eax
0x180010f75  jle     short loc_180010F80
0x180010f77  movzx   ebx, ax
0x180010f7a  or      ebx, 80070000h
0x180010f80  test    ebx, ebx
0x180010f82  jns     short loc_180010FA2
0x180010f84  mov     rcx, rdi
0x180010f87  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010f8d  jmp     short loc_180010FA2
0x180010f8f  mov     rdx, [rsp+88h+arg_20]
0x180010f97  xor     ebx, ebx
0x180010f99  mov     ecx, [rsp+88h+var_48]
0x180010f9d  mov     [rsi], rdi
0x180010fa0  mov     [rdx], ecx
0x180010fa2  mov     eax, ebx
0x180010fa4  add     rsp, 58h
0x180010fa8  pop     r15
0x180010faa  pop     r14
0x180010fac  pop     rdi
0x180010fad  pop     rsi
0x180010fae  pop     rbp
0x180010faf  pop     rbx
0x180010fb0  retn
```
