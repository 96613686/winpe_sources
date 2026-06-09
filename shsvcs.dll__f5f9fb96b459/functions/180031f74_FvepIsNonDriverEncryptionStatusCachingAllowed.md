# FvepIsNonDriverEncryptionStatusCachingAllowed

- ea: `0x180031f74`
- end: `0x180031fff`
- name: `FvepIsNonDriverEncryptionStatusCachingAllowed`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032008`
- `0x180032308`

## callees

- `0x180031f74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031fc7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031fc7`

## string_xrefs

- `0x180031fa2`: `CacheDisable`

## pseudocode

```c
__int64 FvepIsNonDriverEncryptionStatusCachingAllowed()
{
  LSTATUS ValueW; // eax
  int v2; // [rsp+50h] [rbp+8h] BYREF
  DWORD v3; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v3 = 4;
  if ( !dword_18003FB8C )
  {
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\FveDetect",
               L"CacheDisable",
               0x20000010u,
               0,
               &v2,
               &v3);
    if ( (ValueW & 0xFFFFFFFC) == 0 && ValueW != 1 )
    {
      if ( v2 )
        dword_18003E5A4 = 0;
      dword_18003FB8C = 1;
    }
  }
  return (unsigned int)dword_18003E5A4;
}

```

## disassembly

```asm
0x180031f74  mov     r11, rsp
0x180031f77  sub     rsp, 48h
0x180031f7b  cmp     cs:dword_18003FB8C, 0
0x180031f82  mov     [rsp+48h+arg_0], 0
0x180031f8a  mov     [rsp+48h+arg_8], 4
0x180031f92  jnz     short loc_180031FF4
0x180031f94  lea     rax, [r11+10h]
0x180031f98  mov     r9d, 20000010h; dwFlags
0x180031f9e  mov     [r11-18h], rax
0x180031fa2  lea     r8, aCachedisable; "CacheDisable"
0x180031fa9  lea     rax, [r11+8]
0x180031fad  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180031fb4  mov     [r11-20h], rax
0x180031fb8  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180031fbf  mov     qword ptr [r11-28h], 0
0x180031fc7  call    cs:__imp_RegGetValueW
0x180031fcd  test    eax, 0FFFFFFFCh
0x180031fd2  jnz     short loc_180031FF4
0x180031fd4  cmp     eax, 1
0x180031fd7  jz      short loc_180031FF4
0x180031fd9  cmp     [rsp+48h+arg_0], 0
0x180031fde  jz      short loc_180031FEA
0x180031fe0  mov     cs:dword_18003E5A4, 0
0x180031fea  mov     cs:dword_18003FB8C, 1
0x180031ff4  mov     eax, cs:dword_18003E5A4
0x180031ffa  add     rsp, 48h
0x180031ffe  retn
```
