# TraceUpdateConsoleOwner(x,x)

- ea: `0x10009eb2`
- end: `0x10009f52`
- name: `_TraceUpdateConsoleOwner@8`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x10006f22`
- `0x10007715`
- `0x10009977`

## callees

- `0x100086c3`
- `0x10009eb2`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!SetConsoleActiveScreenBuffer` at `0x10009f28`
- `api-ms-win-core-console-l2-1-0!SetConsoleActiveScreenBuffer` at `0x10009f28`

## pseudocode

```c
int __fastcall TraceUpdateConsoleOwner(int a1, int a2)
{
  int v3; // esi
  int v4; // eax
  int v5; // ecx
  unsigned int v6; // edx
  int v7; // eax
  unsigned int v8; // ebx

  v3 = 0;
  v4 = *(_DWORD *)(a1 + 40);
  if ( v4 == 60 )
    v5 = 0;
  else
    v5 = *(_DWORD *)(a1 + 4 * v4 + 308);
  v6 = (a2 + 60 + v4) % 0x3Cu;
  v7 = 0;
  v8 = v6;
  while ( v8 != *(_DWORD *)(a1 + 40) )
  {
    v3 = *(_DWORD *)(a1 + 4 * v8 + 308);
    if ( v3 && (*(_BYTE *)(v3 + 32) & 4) != 0 )
      goto LABEL_11;
    ++v7;
    v8 = (v8 + a2 + 60) % 0x3C;
    if ( v7 >= 60 )
      break;
  }
  if ( v3 && (*(_BYTE *)(v3 + 32) & 4) != 0 )
  {
LABEL_11:
    SetConsoleActiveScreenBuffer(*(HANDLE *)(v3 + 236));
    *(_DWORD *)(a1 + 40) = v8;
    TraceUpdateConsoleTitleA(v3);
    return 0;
  }
  if ( !v5 || (*(_BYTE *)(v5 + 32) & 4) == 0 )
    *(_DWORD *)(a1 + 40) = 60;
  return 0;
}

```

## disassembly

```asm
0x10009eb2  mov     edi, edi
0x10009eb4  push    ebp
0x10009eb5  mov     ebp, esp
0x10009eb7  push    ecx
0x10009eb8  push    ecx
0x10009eb9  push    ebx
0x10009eba  push    esi
0x10009ebb  push    edi
0x10009ebc  mov     edi, ecx
0x10009ebe  mov     [ebp+var_8], edx
0x10009ec1  push    3Ch ; '<'
0x10009ec3  pop     ebx
0x10009ec4  xor     esi, esi
0x10009ec6  mov     eax, [edi+28h]
0x10009ec9  cmp     eax, ebx
0x10009ecb  jz      short loc_10009ED6
0x10009ecd  mov     ecx, [edi+eax*4+134h]
0x10009ed4  jmp     short loc_10009ED8
0x10009ed6  xor     ecx, ecx
0x10009ed8  add     edx, 3Ch ; '<'
0x10009edb  add     eax, edx
0x10009edd  xor     edx, edx
0x10009edf  div     ebx
0x10009ee1  mov     eax, esi
0x10009ee3  mov     ebx, edx
0x10009ee5  cmp     ebx, [edi+28h]
0x10009ee8  jz      short loc_10009F18
0x10009eea  mov     esi, [edi+ebx*4+134h]
0x10009ef1  test    esi, esi
0x10009ef3  jz      short loc_10009EFB
0x10009ef5  test    byte ptr [esi+20h], 4
0x10009ef9  jnz     short loc_10009F22
0x10009efb  inc     eax
0x10009efc  xor     edx, edx
0x10009efe  mov     [ebp+var_4], eax
0x10009f01  mov     eax, [ebp+var_8]
0x10009f04  add     eax, 3Ch ; '<'
0x10009f07  add     eax, ebx
0x10009f09  push    3Ch ; '<'
0x10009f0b  pop     ebx
0x10009f0c  div     ebx
0x10009f0e  mov     eax, [ebp+var_4]
0x10009f11  mov     ebx, edx
0x10009f13  cmp     eax, 3Ch ; '<'
0x10009f16  jl      short loc_10009EE5
0x10009f18  test    esi, esi
0x10009f1a  jz      short loc_10009F3A
0x10009f1c  test    byte ptr [esi+20h], 4
0x10009f20  jz      short loc_10009F3A
0x10009f22  push    dword ptr [esi+0ECh]; hConsoleOutput
0x10009f28  call    ds:__imp__SetConsoleActiveScreenBuffer@4; SetConsoleActiveScreenBuffer(x)
0x10009f2e  mov     ecx, esi
0x10009f30  mov     [edi+28h], ebx
0x10009f33  call    _TraceUpdateConsoleTitleA@4; TraceUpdateConsoleTitleA(x)
0x10009f38  jmp     short loc_10009F4B
0x10009f3a  test    ecx, ecx
0x10009f3c  jz      short loc_10009F44
0x10009f3e  test    byte ptr [ecx+20h], 4
0x10009f42  jnz     short loc_10009F4B
0x10009f44  mov     dword ptr [edi+28h], 3Ch ; '<'
0x10009f4b  pop     edi
0x10009f4c  pop     esi
0x10009f4d  xor     eax, eax
0x10009f4f  pop     ebx
0x10009f50  leave
0x10009f51  retn
```
