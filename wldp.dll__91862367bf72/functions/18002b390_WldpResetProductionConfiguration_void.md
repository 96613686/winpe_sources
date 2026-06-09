# WldpResetProductionConfiguration(void)

- ea: `0x18002b390`
- end: `0x18002b476`
- name: `?WldpResetProductionConfiguration@@YAJXZ`
- size: `230`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002ad60`

## callees

- `0x180018434`
- `0x18002a480`
- `0x18002a900`
- `0x18002b390`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b44d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b44d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b463`

## string_xrefs

- `0x18002b3a8`: `%SystemRoot%\System32\CodeIntegrity\Data`
- `0x18002b3cd`: `%SystemRoot%\System32\CodeIntegrity\Data\WatermarkHSTITestComplete.bin`
- `0x18002b3e2`: `%SystemRoot%\System32\CodeIntegrity\Data\WatermarkSecurityTestComplete.bin`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WldpResetProductionConfiguration(void)
{
  int v0; // ebx
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF
  HLOCAL v3; // [rsp+38h] [rbp+10h] BYREF
  HLOCAL v4; // [rsp+40h] [rbp+18h] BYREF

  hMem = 0;
  v3 = 0;
  v4 = 0;
  if ( (int)ExpandRequiredPaths(L"%SystemRoot%\\System32\\CodeIntegrity\\Data", (unsigned __int16 **)&hMem) < 0
    || (int)ExpandRequiredPaths(
              L"%SystemRoot%\\System32\\CodeIntegrity\\Data\\WatermarkHSTITestComplete.bin",
              (unsigned __int16 **)&v3) < 0
    || (int)ExpandRequiredPaths(
              L"%SystemRoot%\\System32\\CodeIntegrity\\Data\\WatermarkSecurityTestComplete.bin",
              (unsigned __int16 **)&v4) < 0 )
  {
    v0 = -2147024882;
  }
  else
  {
    v0 = InitializeWatermarkPath((const unsigned __int16 *)hMem);
    if ( v0 >= 0 )
    {
      v0 = DeleteWatermarkState((const unsigned __int16 *)v3, 0);
      if ( (int)(v0 + 0x80000000) < 0 || v0 == -2147024894 )
      {
        v0 = DeleteWatermarkState((const unsigned __int16 *)v4, 0);
        if ( ((v0 + 0x80000000) & 0x80000000) != 0 || v0 == -2147024894 )
          v0 = 0;
      }
    }
  }
  LocalFree(hMem);
  LocalFree(v3);
  LocalFree(v4);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18002b390  mov     rax, rsp
0x18002b393  mov     [rax+20h], rbx
0x18002b397  push    rbp
0x18002b398  sub     rsp, 20h
0x18002b39c  lea     rdx, [rax+8]; unsigned __int16 **
0x18002b3a0  mov     qword ptr [rax+8], 0
0x18002b3a8  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18002b3af  mov     qword ptr [rax+10h], 0
0x18002b3b7  mov     qword ptr [rax+18h], 0
0x18002b3bf  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18002b3c4  test    eax, eax
0x18002b3c6  js      short loc_18002B443
0x18002b3c8  lea     rdx, [rsp+28h+arg_8]; unsigned __int16 **
0x18002b3cd  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18002b3d4  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18002b3d9  test    eax, eax
0x18002b3db  js      short loc_18002B443
0x18002b3dd  lea     rdx, [rsp+28h+arg_10]; unsigned __int16 **
0x18002b3e2  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18002b3e9  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18002b3ee  test    eax, eax
0x18002b3f0  js      short loc_18002B443
0x18002b3f2  mov     rcx, [rsp+28h+hMem]; unsigned __int16 *
0x18002b3f7  call    ?InitializeWatermarkPath@@YAJPEBG@Z; InitializeWatermarkPath(ushort const *)
0x18002b3fc  mov     ebx, eax
0x18002b3fe  test    eax, eax
0x18002b400  js      short loc_18002B448
0x18002b402  mov     rcx, [rsp+28h+arg_8]; unsigned __int16 *
0x18002b407  xor     edx, edx; unsigned __int16 *
0x18002b409  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b40e  mov     ebp, 80000000h
0x18002b413  mov     ebx, eax
0x18002b415  add     eax, ebp
0x18002b417  test    ebp, eax
0x18002b419  jnz     short loc_18002B423
0x18002b41b  cmp     ebx, 80070002h
0x18002b421  jnz     short loc_18002B448
0x18002b423  mov     rcx, [rsp+28h+arg_10]; unsigned __int16 *
0x18002b428  xor     edx, edx; unsigned __int16 *
0x18002b42a  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b42f  mov     ebx, eax
0x18002b431  add     eax, ebp
0x18002b433  test    ebp, eax
0x18002b435  jnz     short loc_18002B43F
0x18002b437  cmp     ebx, 80070002h
0x18002b43d  jnz     short loc_18002B448
0x18002b43f  xor     ebx, ebx
0x18002b441  jmp     short loc_18002B448
0x18002b443  mov     ebx, 8007000Eh
0x18002b448  mov     rcx, [rsp+28h+hMem]; hMem
0x18002b44d  call    cs:__imp_LocalFree
0x18002b453  mov     rcx, [rsp+28h+arg_8]; hMem
0x18002b458  call    cs:__imp_LocalFree
0x18002b45e  mov     rcx, [rsp+28h+arg_10]; hMem
0x18002b463  call    cs:__imp_LocalFree
0x18002b469  mov     eax, ebx
0x18002b46b  mov     rbx, [rsp+28h+arg_18]
0x18002b470  add     rsp, 20h
0x18002b474  pop     rbp
0x18002b475  retn
```
