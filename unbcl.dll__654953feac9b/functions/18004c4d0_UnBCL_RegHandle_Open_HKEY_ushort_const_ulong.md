# UnBCL::RegHandle::Open(HKEY__ *,ushort const *,ulong)

- ea: `0x18004c4d0`
- end: `0x18004c52e`
- name: `?Open@RegHandle@UnBCL@@QEAAHPEAUHKEY__@@PEBGK@Z`
- size: `94`
- prototype: `int(UnBCL::RegHandle *__hidden this, HKEY, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18004c140`
- `0x18004c4d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18004c501`
- `ADVAPI32!RegOpenKeyExW` at `0x18004c501`
- `KERNEL32!SetLastError` at `0x18004c516`
- `KERNEL32!SetLastError` at `0x18004c516`

## pseudocode

```c
_BOOL8 __fastcall UnBCL::RegHandle::Open(UnBCL::RegHandle *this, HKEY a2, const unsigned __int16 *a3, REGSAM a4)
{
  HKEY *phkResult; // r14
  LSTATUS v9; // eax
  LSTATUS v10; // ebx

  UnBCL::RegHandle::Close(this);
  phkResult = (HKEY *)((char *)this + 8);
  v9 = RegOpenKeyExW(a2, a3, 0, a4, phkResult);
  v10 = v9;
  if ( v9 )
  {
    *phkResult = 0;
    SetLastError(v9);
  }
  return v10 == 0;
}

```

## disassembly

```asm
0x18004c4d0  push    rbx
0x18004c4d2  push    rbp
0x18004c4d3  push    rsi
0x18004c4d4  push    rdi
0x18004c4d5  push    r14
0x18004c4d7  sub     rsp, 30h
0x18004c4db  mov     edi, r9d
0x18004c4de  mov     rsi, r8
0x18004c4e1  mov     rbp, rdx
0x18004c4e4  mov     r14, rcx
0x18004c4e7  call    ?Close@RegHandle@UnBCL@@QEAAXXZ; UnBCL::RegHandle::Close(void)
0x18004c4ec  add     r14, 8
0x18004c4f0  mov     r9d, edi; samDesired
0x18004c4f3  xor     r8d, r8d; ulOptions
0x18004c4f6  mov     [rsp+58h+phkResult], r14; phkResult
0x18004c4fb  mov     rdx, rsi; lpSubKey
0x18004c4fe  mov     rcx, rbp; hKey
0x18004c501  call    cs:__imp_RegOpenKeyExW
0x18004c507  mov     ebx, eax
0x18004c509  test    eax, eax
0x18004c50b  jz      short loc_18004C51C
0x18004c50d  mov     ecx, eax; dwErrCode
0x18004c50f  mov     qword ptr [r14], 0
0x18004c516  call    cs:__imp_SetLastError
0x18004c51c  xor     eax, eax
0x18004c51e  test    ebx, ebx
0x18004c520  setz    al
0x18004c523  add     rsp, 30h
0x18004c527  pop     r14
0x18004c529  pop     rdi
0x18004c52a  pop     rsi
0x18004c52b  pop     rbp
0x18004c52c  pop     rbx
0x18004c52d  retn
```
