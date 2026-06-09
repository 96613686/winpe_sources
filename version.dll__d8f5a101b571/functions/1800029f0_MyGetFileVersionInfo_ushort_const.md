# MyGetFileVersionInfo(ushort const *)

- ea: `0x1800029f0`
- end: `0x180002a63`
- name: `?MyGetFileVersionInfo@@YAPEAUtagVS_VERSION@@PEBG@Z`
- size: `115`
- prototype: `struct tagVS_VERSION *__fastcall(LPCWSTR lptstrFilename)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x1800029f0`

## import_xrefs

- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180002a26`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180002a26`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002a0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002a4b`

## pseudocode

```c
struct tagVS_VERSION *__fastcall MyGetFileVersionInfo(LPCWSTR lptstrFilename)
{
  unsigned __int16 v2; // di
  unsigned __int16 *v3; // rax
  unsigned __int16 *v4; // rbx

  v2 = 2048;
  while ( 1 )
  {
    v3 = (unsigned __int16 *)LocalAlloc(0, v2);
    v4 = v3;
    if ( !v3 )
      break;
    if ( !GetFileVersionInfoW(lptstrFilename, 0, v2, v3) )
    {
      LocalFree(v4);
      return 0;
    }
    if ( v2 >= *v4 )
      return (struct tagVS_VERSION *)v4;
    v2 = *v4;
    LocalFree(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800029f0  mov     [rsp+arg_0], rbx
0x1800029f5  mov     [rsp+arg_8], rsi
0x1800029fa  push    rdi
0x1800029fb  sub     rsp, 20h
0x1800029ff  mov     rsi, rcx
0x180002a02  mov     edi, 800h
0x180002a07  movzx   edx, di; uBytes
0x180002a0a  xor     ecx, ecx; uFlags
0x180002a0c  call    cs:__imp_LocalAlloc
0x180002a12  mov     rbx, rax
0x180002a15  test    rax, rax
0x180002a18  jz      short loc_180002A51
0x180002a1a  movzx   r8d, di; dwLen
0x180002a1e  mov     r9, rax; lpData
0x180002a21  xor     edx, edx; dwHandle
0x180002a23  mov     rcx, rsi; lptstrFilename
0x180002a26  call    cs:__imp_GetFileVersionInfoW
0x180002a2c  test    eax, eax
0x180002a2e  jz      short loc_180002A48
0x180002a30  cmp     di, [rbx]
0x180002a33  jnb     short loc_180002A43
0x180002a35  movzx   edi, word ptr [rbx]
0x180002a38  mov     rcx, rbx; hMem
0x180002a3b  call    cs:__imp_LocalFree
0x180002a41  jmp     short loc_180002A07
0x180002a43  mov     rax, rbx
0x180002a46  jmp     short loc_180002A53
0x180002a48  mov     rcx, rbx; hMem
0x180002a4b  call    cs:__imp_LocalFree
0x180002a51  xor     eax, eax
0x180002a53  mov     rbx, [rsp+28h+arg_0]
0x180002a58  mov     rsi, [rsp+28h+arg_8]
0x180002a5d  add     rsp, 20h
0x180002a61  pop     rdi
0x180002a62  retn
```
