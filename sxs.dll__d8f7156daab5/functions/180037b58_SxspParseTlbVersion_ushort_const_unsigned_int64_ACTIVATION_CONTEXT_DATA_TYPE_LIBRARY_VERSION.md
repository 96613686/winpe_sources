# SxspParseTlbVersion(ushort const *,unsigned __int64,_ACTIVATION_CONTEXT_DATA_TYPE_LIBRARY_VERSION *)

- ea: `0x180037b58`
- end: `0x180037c6c`
- name: `?SxspParseTlbVersion@@YAHPEBG_KPEAU_ACTIVATION_CONTEXT_DATA_TYPE_LIBRARY_VERSION@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, struct _ACTIVATION_CONTEXT_DATA_TYPE_LIBRARY_VERSION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800358d0`
- `0x180037ef0`

## callees

- `0x18000c000`
- `0x180037b58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bb7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037bb7`

## string_xrefs

- `0x180037be9`: `SXS.DLL: No dots found in a TLB version number.\n`
- `0x180037ba1`: `SXS.DLL: Found two or more dots in a TLB version number.\n`
- `0x180037bdb`: `SXS.DLL: Found characters other than . and 0-9 in a TLB version number.\n`

## pseudocode

```c
__int64 __fastcall SxspParseTlbVersion(
        const unsigned __int16 *a1,
        __int64 a2,
        struct _ACTIVATION_CONTEXT_DATA_TYPE_LIBRARY_VERSION *a3)
{
  unsigned int v5; // ebx
  int i; // ecx
  const unsigned __int16 *v7; // r10
  __int64 j; // r8
  unsigned __int16 v9; // r8
  const unsigned __int16 *v10; // r10
  const unsigned __int16 *v11; // rdx
  __int16 v12; // cx
  __int16 v13; // cx
  int v15; // [rsp+30h] [rbp+8h]

  v5 = 0;
  for ( i = 0; a2; --a2 )
  {
    if ( a1[a2 - 1] )
      break;
  }
  v7 = a1;
  for ( j = a2; j; --j )
  {
    if ( *v7 == 46 )
    {
      if ( (unsigned int)++i >= 2 )
      {
        FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Found two or more dots in a TLB version number.\n");
LABEL_9:
        SetLastError(0x36B5u);
        return v5;
      }
    }
    else if ( (unsigned __int16)(*v7 - 48) > 9u )
    {
      FusionpDbgPrintEx(0xC0000000, "SXS.DLL: Found characters other than . and 0-9 in a TLB version number.\n");
      goto LABEL_9;
    }
    ++v7;
  }
  if ( !i )
  {
    FusionpDbgPrintEx(0xC0000000, "SXS.DLL: No dots found in a TLB version number.\n");
    goto LABEL_9;
  }
  v9 = *a1;
  v10 = &a1[a2];
  v11 = a1 + 1;
  v12 = 0;
  while ( v9 != 46 )
  {
    v12 = v9 - 48 + 10 * v12;
    v9 = *v11++;
  }
  LOWORD(v15) = v12;
  v13 = 0;
  while ( v11 < v10 )
    v13 = *v11++ + 10 * v13 - 48;
  HIWORD(v15) = v13;
  v5 = 1;
  *(_DWORD *)a3 = v15;
  return v5;
}

```

## disassembly

```asm
0x180037b58  mov     [rsp+arg_8], rbx
0x180037b5d  push    rdi
0x180037b5e  sub     rsp, 20h
0x180037b62  xor     edi, edi
0x180037b64  mov     r9, rcx
0x180037b67  mov     [rsp+28h+arg_0], edi
0x180037b6b  mov     r11, r8
0x180037b6e  mov     ebx, edi
0x180037b70  mov     ecx, edi
0x180037b72  test    rdx, rdx
0x180037b75  jz      short loc_180037B85
0x180037b77  cmp     [r9+rdx*2-2], di
0x180037b7d  jnz     short loc_180037B85
0x180037b7f  sub     rdx, 1
0x180037b83  jnz     short loc_180037B77
0x180037b85  mov     r10, r9
0x180037b88  mov     r8, rdx
0x180037b8b  test    r8, r8
0x180037b8e  jz      short loc_180037BE4
0x180037b90  movzx   eax, word ptr [r10]
0x180037b94  cmp     ax, 2Eh ; '.'
0x180037b98  jnz     short loc_180037BC8
0x180037b9a  inc     ecx
0x180037b9c  cmp     ecx, 2
0x180037b9f  jb      short loc_180037BD2
0x180037ba1  lea     rdx, aSxsDllFoundTwo; "SXS.DLL: Found two or more dots in a TL"...
0x180037ba8  mov     ecx, 0C0000000h; unsigned int
0x180037bad  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180037bb2  mov     ecx, 36B5h; dwErrCode
0x180037bb7  call    cs:__imp_SetLastError
0x180037bbe  nop     dword ptr [rax+rax+00h]
0x180037bc3  jmp     loc_180037C5E
0x180037bc8  sub     ax, 30h ; '0'
0x180037bcc  cmp     ax, 9
0x180037bd0  ja      short loc_180037BDB
0x180037bd2  dec     r8
0x180037bd5  add     r10, 2
0x180037bd9  jmp     short loc_180037B8B
0x180037bdb  lea     rdx, aSxsDllFoundCha; "SXS.DLL: Found characters other than . "...
0x180037be2  jmp     short loc_180037BA8
0x180037be4  cmp     ecx, 1
0x180037be7  jnb     short loc_180037BF2
0x180037be9  lea     rdx, aSxsDllNoDotsFo; "SXS.DLL: No dots found in a TLB version"...
0x180037bf0  jmp     short loc_180037BA8
0x180037bf2  movzx   r8d, word ptr [r9]
0x180037bf6  lea     r10, [r9+rdx*2]
0x180037bfa  lea     rdx, [r9+2]
0x180037bfe  mov     ecx, edi
0x180037c00  jmp     short loc_180037C20
0x180037c02  movzx   eax, cx
0x180037c05  sub     r8w, 30h ; '0'
0x180037c0a  shl     ax, 2
0x180037c0e  add     cx, ax
0x180037c11  add     cx, cx
0x180037c14  add     cx, r8w
0x180037c18  movzx   r8d, word ptr [rdx]
0x180037c1c  add     rdx, 2
0x180037c20  cmp     r8w, 2Eh ; '.'
0x180037c25  jnz     short loc_180037C02
0x180037c27  mov     word ptr [rsp+28h+arg_0], cx
0x180037c2c  mov     ecx, edi
0x180037c2e  jmp     short loc_180037C48
0x180037c30  movzx   eax, cx
0x180037c33  shl     ax, 2
0x180037c37  add     cx, ax
0x180037c3a  add     cx, cx
0x180037c3d  sub     cx, 30h ; '0'
0x180037c41  add     cx, [rdx]
0x180037c44  add     rdx, 2
0x180037c48  cmp     rdx, r10
0x180037c4b  jb      short loc_180037C30
0x180037c4d  mov     word ptr [rsp+28h+arg_0+2], cx
0x180037c52  mov     ebx, 1
0x180037c57  mov     eax, [rsp+28h+arg_0]
0x180037c5b  mov     [r11], eax
0x180037c5e  mov     eax, ebx
0x180037c60  mov     rbx, [rsp+28h+arg_8]
0x180037c65  add     rsp, 20h
0x180037c69  pop     rdi
0x180037c6a  retn
```
