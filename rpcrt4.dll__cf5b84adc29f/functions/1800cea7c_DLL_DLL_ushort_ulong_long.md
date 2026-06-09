# DLL::DLL(ushort *,ulong,long *)

- ea: `0x1800cea7c`
- end: `0x1800ceb51`
- name: `??0DLL@@QEAA@PEAGKPEAJ@Z`
- size: `213`
- prototype: `DLL *(DLL *__hidden this, unsigned __int16 *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180057b70`
- `0x1800a214c`

## callees

- `0x1800cea7c`

## import_xrefs

- `ntdll!_wcsicmp` at `0x1800ceaa5`
- `ntdll!_wcsicmp` at `0x1800ceaa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceadd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ceadd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ceac9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ceac9`

## string_xrefs

- `0x1800cea98`: `rpcrt4.dll`

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
0x1800cea7c  mov     [rsp+arg_0], rbx
0x1800cea81  mov     [rsp+arg_8], rsi
0x1800cea86  push    rdi
0x1800cea87  sub     rsp, 40h
0x1800cea8b  mov     rsi, rdx
0x1800cea8e  mov     dword ptr [r9], 0
0x1800cea95  mov     rbx, rcx
0x1800cea98  lea     rdx, aRpcrt4Dll_0; "rpcrt4.dll"
0x1800cea9f  mov     rcx, rsi; String1
0x1800ceaa2  mov     rdi, r9
0x1800ceaa5  call    cs:__imp__wcsicmp
0x1800ceaac  nop     dword ptr [rax+rax+00h]
0x1800ceab1  test    eax, eax
0x1800ceab3  jnz     short loc_1800CEABE
0x1800ceab5  mov     qword ptr [rbx], 0
0x1800ceabc  jmp     short loc_1800CEB3D
0x1800ceabe  xor     edx, edx; hFile
0x1800ceac0  mov     r8d, 800h; dwFlags
0x1800ceac6  mov     rcx, rsi; lpLibFileName
0x1800ceac9  call    cs:__imp_LoadLibraryExW
0x1800cead0  nop     dword ptr [rax+rax+00h]
0x1800cead5  mov     [rbx], rax
0x1800cead8  test    rax, rax
0x1800ceadb  jnz     short loc_1800CEB3D
0x1800ceadd  call    cs:__imp_GetLastError
0x1800ceae4  nop     dword ptr [rax+rax+00h]
0x1800ceae9  mov     r8d, 0Eh
0x1800ceaef  mov     [rsp+48h+var_24], 5AAh
0x1800ceaf7  mov     [rsp+48h+var_28], r8d
0x1800ceafc  xor     edx, edx
0x1800ceafe  mov     [rsp+48h+var_20], 8
0x1800ceb06  mov     [rsp+48h+var_1C], 5ADh
0x1800ceb0e  mov     [rsp+48h+var_18], 5AFh
0x1800ceb16  mov     [rsp+48h+var_14], 718h
0x1800ceb1e  cmp     [rsp+rdx*4+48h+var_28], eax
0x1800ceb22  jz      short loc_1800CEB3A
0x1800ceb24  inc     edx
0x1800ceb26  cmp     edx, 6
0x1800ceb29  jb      short loc_1800CEB1E
0x1800ceb2b  cmp     eax, 45Ah
0x1800ceb30  jz      short loc_1800CEB3A
0x1800ceb32  mov     dword ptr [rdi], 57h ; 'W'
0x1800ceb38  jmp     short loc_1800CEB3D
0x1800ceb3a  mov     [rdi], r8d
0x1800ceb3d  mov     rsi, [rsp+48h+arg_8]
0x1800ceb42  mov     rax, rbx
0x1800ceb45  mov     rbx, [rsp+48h+arg_0]
0x1800ceb4a  add     rsp, 40h
0x1800ceb4e  pop     rdi
0x1800ceb4f  retn
```
