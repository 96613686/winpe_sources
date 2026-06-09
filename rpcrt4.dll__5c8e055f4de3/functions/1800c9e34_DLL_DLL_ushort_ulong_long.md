# DLL::DLL(ushort *,ulong,long *)

- ea: `0x1800c9e34`
- end: `0x1800c9ef6`
- name: `??0DLL@@QEAA@PEAGKPEAJ@Z`
- size: `194`
- prototype: `DLL *(DLL *__hidden this, unsigned __int16 *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180045d90`
- `0x18009e860`

## callees

- `0x1800c9e34`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800c9e5d`
- `ntdll!_wcsicmp` at `0x1800c9e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9e89`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c9e7b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c9e7b`

## string_xrefs

- `0x1800c9e50`: `rpcrt4.dll`

## pseudocode

```c
DLL *__fastcall DLL::DLL(DLL *this, unsigned __int16 *a2, __int64 a3, int *a4)
{
  HMODULE Library; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx
  _DWORD v11[10]; // [rsp+20h] [rbp-28h]

  *a4 = 0;
  if ( _wcsicmp(a2, L"rpcrt4.dll") )
  {
    Library = LoadLibraryExW(a2, 0, 0x800u);
    *(_QWORD *)this = Library;
    if ( !Library )
    {
      LastError = GetLastError();
      v11[1] = 1450;
      v11[0] = 14;
      v9 = 0;
      v11[2] = 8;
      v11[3] = 1453;
      v11[4] = 1455;
      v11[5] = 1816;
      while ( v11[v9] != LastError )
      {
        v9 = (unsigned int)(v9 + 1);
        if ( (unsigned int)v9 >= 6 )
        {
          if ( LastError != 1114 )
          {
            *a4 = 87;
            return this;
          }
          break;
        }
      }
      *a4 = 14;
    }
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x1800c9e34  mov     [rsp+arg_0], rbx
0x1800c9e39  mov     [rsp+arg_8], rsi
0x1800c9e3e  push    rdi
0x1800c9e3f  sub     rsp, 40h
0x1800c9e43  mov     rsi, rdx
0x1800c9e46  mov     dword ptr [r9], 0
0x1800c9e4d  mov     rbx, rcx
0x1800c9e50  lea     rdx, aRpcrt4Dll_0; "rpcrt4.dll"
0x1800c9e57  mov     rcx, rsi; String1
0x1800c9e5a  mov     rdi, r9
0x1800c9e5d  call    cs:__imp__wcsicmp
0x1800c9e63  test    eax, eax
0x1800c9e65  jnz     short loc_1800C9E70
0x1800c9e67  mov     qword ptr [rbx], 0
0x1800c9e6e  jmp     short loc_1800C9EE3
0x1800c9e70  xor     edx, edx; hFile
0x1800c9e72  mov     r8d, 800h; dwFlags
0x1800c9e78  mov     rcx, rsi; lpLibFileName
0x1800c9e7b  call    cs:__imp_LoadLibraryExW
0x1800c9e81  mov     [rbx], rax
0x1800c9e84  test    rax, rax
0x1800c9e87  jnz     short loc_1800C9EE3
0x1800c9e89  call    cs:__imp_GetLastError
0x1800c9e8f  mov     r8d, 0Eh
0x1800c9e95  mov     [rsp+48h+var_24], 5AAh
0x1800c9e9d  mov     [rsp+48h+var_28], r8d
0x1800c9ea2  xor     edx, edx
0x1800c9ea4  mov     [rsp+48h+var_20], 8
0x1800c9eac  mov     [rsp+48h+var_1C], 5ADh
0x1800c9eb4  mov     [rsp+48h+var_18], 5AFh
0x1800c9ebc  mov     [rsp+48h+var_14], 718h
0x1800c9ec4  cmp     [rsp+rdx*4+48h+var_28], eax
0x1800c9ec8  jz      short loc_1800C9EE0
0x1800c9eca  inc     edx
0x1800c9ecc  cmp     edx, 6
0x1800c9ecf  jb      short loc_1800C9EC4
0x1800c9ed1  cmp     eax, 45Ah
0x1800c9ed6  jz      short loc_1800C9EE0
0x1800c9ed8  mov     dword ptr [rdi], 57h ; 'W'
0x1800c9ede  jmp     short loc_1800C9EE3
0x1800c9ee0  mov     [rdi], r8d
0x1800c9ee3  mov     rsi, [rsp+48h+arg_8]
0x1800c9ee8  mov     rax, rbx
0x1800c9eeb  mov     rbx, [rsp+48h+arg_0]
0x1800c9ef0  add     rsp, 40h
0x1800c9ef4  pop     rdi
0x1800c9ef5  retn
```
