# Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)

- ea: `0x18001e0a8`
- end: `0x18001e145`
- name: `??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ`
- size: `157`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001e334`
- `0x180021398`
- `0x180023b40`
- `0x180024ea8`
- `0x180026640`
- `0x180026be4`
- `0x18002bef0`

## callees

- `0x18001e0a8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001e120`
- `KERNEL32!GetProcAddress` at `0x18001e120`
- `KERNEL32!LoadLibraryExW` at `0x18001e0e1`
- `KERNEL32!LoadLibraryExW` at `0x18001e103`
- `KERNEL32!LoadLibraryExW` at `0x18001e0e1`
- `KERNEL32!LoadLibraryExW` at `0x18001e103`

## pseudocode

```c
FARPROC __fastcall Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(__int64 *a1)
{
  FARPROC result; // rax
  __int64 v3; // rdi
  const CHAR *v4; // rsi
  HMODULE Library; // rax
  const WCHAR *v6; // rcx

  if ( *((_BYTE *)a1 + 24) )
    return (FARPROC)a1[2];
  v3 = *a1;
  v4 = (const CHAR *)a1[1];
  if ( *(_BYTE *)(*a1 + 24) )
  {
    Library = *(HMODULE *)v3;
  }
  else
  {
    Library = LoadLibraryExW(*(LPCWSTR *)(v3 + 8), 0, 0);
    *(_QWORD *)v3 = Library;
    if ( !Library )
    {
      v6 = *(const WCHAR **)(v3 + 16);
      if ( v6 )
      {
        Library = LoadLibraryExW(v6, 0, 0);
        *(_QWORD *)v3 = Library;
      }
      else
      {
        Library = 0;
      }
    }
    *(_BYTE *)(v3 + 24) = 1;
  }
  result = GetProcAddress(Library, v4);
  a1[2] = (__int64)result;
  *((_BYTE *)a1 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x18001e0a8  mov     [rsp+arg_0], rbx
0x18001e0ad  mov     [rsp+arg_8], rsi
0x18001e0b2  push    rdi
0x18001e0b3  sub     rsp, 20h
0x18001e0b7  cmp     byte ptr [rcx+18h], 0
0x18001e0bb  mov     rbx, rcx
0x18001e0be  jz      short loc_18001E0C6
0x18001e0c0  mov     rax, [rcx+10h]
0x18001e0c4  jmp     short loc_18001E134
0x18001e0c6  mov     rdi, [rcx]
0x18001e0c9  mov     rsi, [rcx+8]
0x18001e0cd  cmp     byte ptr [rdi+18h], 0
0x18001e0d1  jz      short loc_18001E0D8
0x18001e0d3  mov     rax, [rdi]
0x18001e0d6  jmp     short loc_18001E11A
0x18001e0d8  mov     rcx, [rdi+8]; lpLibFileName
0x18001e0dc  xor     r8d, r8d; dwFlags
0x18001e0df  xor     edx, edx; hFile
0x18001e0e1  call    cs:__imp_LoadLibraryExW
0x18001e0e8  nop     dword ptr [rax+rax+00h]
0x18001e0ed  mov     [rdi], rax
0x18001e0f0  test    rax, rax
0x18001e0f3  jnz     short loc_18001E116
0x18001e0f5  mov     rcx, [rdi+10h]; lpLibFileName
0x18001e0f9  test    rcx, rcx
0x18001e0fc  jz      short loc_18001E114
0x18001e0fe  xor     r8d, r8d; dwFlags
0x18001e101  xor     edx, edx; hFile
0x18001e103  call    cs:__imp_LoadLibraryExW
0x18001e10a  nop     dword ptr [rax+rax+00h]
0x18001e10f  mov     [rdi], rax
0x18001e112  jmp     short loc_18001E116
0x18001e114  xor     eax, eax
0x18001e116  mov     byte ptr [rdi+18h], 1
0x18001e11a  mov     rdx, rsi; lpProcName
0x18001e11d  mov     rcx, rax; hModule
0x18001e120  call    cs:__imp_GetProcAddress
0x18001e127  nop     dword ptr [rax+rax+00h]
0x18001e12c  mov     [rbx+10h], rax
0x18001e130  mov     byte ptr [rbx+18h], 1
0x18001e134  mov     rbx, [rsp+28h+arg_0]
0x18001e139  mov     rsi, [rsp+28h+arg_8]
0x18001e13e  add     rsp, 20h
0x18001e142  pop     rdi
0x18001e143  retn
```
