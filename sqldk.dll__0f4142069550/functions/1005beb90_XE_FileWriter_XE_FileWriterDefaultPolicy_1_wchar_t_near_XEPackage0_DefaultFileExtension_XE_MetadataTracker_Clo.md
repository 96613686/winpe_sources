# XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CloseLog(XE_Log *,unsigned __int64)

- ea: `0x1005beb90`
- end: `0x1005bec45`
- name: `?CloseLog@?$XE_FileWriter@V?$XE_FileWriterDefaultPolicy@$00$1?DefaultFileExtension@XEPackage0@@3PA_WA@@VXE_MetadataTracker@@@@AEAAXPEAVXE_Log@@_K@Z`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x10043c550`
- `0x1005be470`
- `0x1005bec50`

## callees

- `0x1005beb90`

## import_xrefs

- `KERNEL32!SetEndOfFile` at `0x1005bebf1`
- `KERNEL32!SetEndOfFile` at `0x1005bebf1`
- `KERNEL32!SetFilePointerEx` at `0x1005bebe0`
- `KERNEL32!SetFilePointerEx` at `0x1005bebe0`
- `KERNEL32!CloseHandle` at `0x1005bec2c`
- `KERNEL32!CloseHandle` at `0x1005bec2c`

## pseudocode

```c
void __fastcall XE_FileWriter<XE_FileWriterDefaultPolicy<1,&wchar_t near * XEPackage0::DefaultFileExtension>,XE_MetadataTracker>::CloseLog(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  void *v3; // r10
  unsigned __int64 v5; // rax
  void *v6; // rcx

  v3 = *(void **)(a2 + 632);
  if ( v3 == (void *)-1LL )
  {
    *(_QWORD *)(a2 + 648) = 0;
  }
  else
  {
    if ( a3 )
      v5 = *(unsigned int *)(a2 + 8)
         * (((unsigned __int64)*(unsigned int *)(a2 + 8) + a3 - 1)
          / *(unsigned int *)(a2 + 8));
    else
      v5 = 0;
    if ( *(_DWORD *)(a2 + 52) )
    {
      qword_100715080(v3, v5);
    }
    else if ( SetFilePointerEx(v3, (LARGE_INTEGER)v5, 0, 0) )
    {
      SetEndOfFile(*(HANDLE *)(a2 + 632));
    }
    v6 = *(void **)(a2 + 632);
    if ( *(_DWORD *)(a2 + 52) )
    {
      qword_100715090(v6);
    }
    else if ( v6 != (void *)-1LL )
    {
      CloseHandle(v6);
    }
    *(_QWORD *)(a2 + 632) = -1;
    *(_QWORD *)(a2 + 648) = 0;
  }
}

```

## disassembly

```asm
0x1005beb90  push    rbx
0x1005beb92  sub     rsp, 20h
0x1005beb96  mov     r10, [rdx+278h]
0x1005beb9d  mov     rbx, rdx
0x1005beba0  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x1005beba4  jz      loc_1005BEC34
0x1005bebaa  test    r8, r8
0x1005bebad  jz      short loc_1005BEBC4
0x1005bebaf  mov     ecx, [rdx+8]
0x1005bebb2  lea     rax, [r8-1]
0x1005bebb6  add     rax, rcx
0x1005bebb9  xor     edx, edx
0x1005bebbb  div     rcx
0x1005bebbe  imul    rax, rcx
0x1005bebc2  jmp     short loc_1005BEBC6
0x1005bebc4  xor     eax, eax
0x1005bebc6  cmp     dword ptr [rbx+34h], 0
0x1005bebca  mov     rdx, rax; liDistanceToMove
0x1005bebcd  mov     rcx, r10; hFile
0x1005bebd0  jz      short loc_1005BEBDA
0x1005bebd2  call    cs:qword_100715080
0x1005bebd8  jmp     short loc_1005BEBF7
0x1005bebda  xor     r9d, r9d; dwMoveMethod
0x1005bebdd  xor     r8d, r8d; lpNewFilePointer
0x1005bebe0  call    cs:__imp_SetFilePointerEx
0x1005bebe6  test    eax, eax
0x1005bebe8  jz      short loc_1005BEBF7
0x1005bebea  mov     rcx, [rbx+278h]; hFile
0x1005bebf1  call    cs:__imp_SetEndOfFile
0x1005bebf7  cmp     dword ptr [rbx+34h], 0
0x1005bebfb  mov     rcx, [rbx+278h]; hObject
0x1005bec02  jz      short loc_1005BEC26
0x1005bec04  call    cs:qword_100715090
0x1005bec0a  mov     qword ptr [rbx+278h], 0FFFFFFFFFFFFFFFFh
0x1005bec15  mov     qword ptr [rbx+288h], 0
0x1005bec20  add     rsp, 20h
0x1005bec24  pop     rbx
0x1005bec25  retn
0x1005bec26  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1005bec2a  jz      short loc_1005BEC0A
0x1005bec2c  call    cs:__imp_CloseHandle
0x1005bec32  jmp     short loc_1005BEC0A
0x1005bec34  mov     qword ptr [rdx+288h], 0
0x1005bec3f  add     rsp, 20h
0x1005bec43  pop     rbx
0x1005bec44  retn
```
