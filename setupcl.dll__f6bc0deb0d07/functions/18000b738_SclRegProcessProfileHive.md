# SclRegProcessProfileHive

- ea: `0x18000b738`
- end: `0x18000b905`
- name: `SclRegProcessProfileHive`
- size: `461`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18000bc68`

## callees

- `0x180005a20`
- `0x1800092bc`
- `0x180009374`
- `0x180009904`
- `0x18000a524`
- `0x18000ac28`
- `0x18000b738`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000b8e4`
- `ntdll!RtlFreeHeap` at `0x18000b8e4`

## string_xrefs

- `0x18000b810`: `Found hive [%ws] already loaded at: [%ws]`

## pseudocode

```c
__int64 __fastcall SclRegProcessProfileHive(__int64 a1, const WCHAR *a2)
{
  __int64 v2; // r12
  __int64 v5; // r14
  int CanonicalMountKeyPath; // eax
  WCHAR *v7; // rdi
  int v8; // ebx
  int UnloadHive; // eax
  bool v10; // bp
  int LoadedHive; // eax
  int v12; // eax
  __int64 v14; // [rsp+30h] [rbp-38h]
  PVOID P; // [rsp+70h] [rbp+8h] BYREF

  v2 = a1 + 1152;
  P = 0;
  v5 = a1 + 1152;
  if ( !a1 )
    v5 = 0;
  SclLogGenericMessage(
    v5,
    1,
    (int)SclEvent_Generic_Info,
    1782,
    (__int64)"SclRegProcessProfileHive",
    "Processing profile hive: [%ws]",
    a2);
  SclEtwWriteString(v2, (__int64)SclEvent_ProcessRegistryHive_Start, (__int64)a2);
  CanonicalMountKeyPath = SclRegGetCanonicalMountKeyPath((__int64)a2, (wchar_t **)&P);
  v7 = (WCHAR *)P;
  v8 = CanonicalMountKeyPath;
  if ( CanonicalMountKeyPath >= 0 )
  {
    UnloadHive = SclRegLoadUnloadHive(1, (const WCHAR *)P, a2);
    v8 = UnloadHive;
    v10 = UnloadHive >= 0;
    if ( UnloadHive == -1073741757 )
    {
      LoadedHive = SclRegFindLoadedHive(a2, &P);
      v7 = (WCHAR *)P;
      if ( LoadedHive >= 0 )
      {
        SclLogGenericMessage(
          v5,
          1,
          (int)SclEvent_Generic_Info,
          1818,
          (__int64)"SclRegProcessProfileHive",
          "Found hive [%ws] already loaded at: [%ws]",
          a2,
          P);
        goto LABEL_8;
      }
    }
    else if ( UnloadHive >= 0 )
    {
LABEL_8:
      v12 = SclRegProcessKey(a1, v7, 0);
      v8 = v12;
      if ( v12 < 0 )
      {
        LODWORD(v14) = v12;
        SclLogGenericMessage(
          v5,
          3,
          (int)SclEvent_Generic_Error,
          1831,
          (__int64)"SclRegProcessProfileHive",
          "(%lx): Failed to process user hive [%ws]",
          v14,
          a2);
      }
    }
    if ( v10 )
    {
      if ( v8 < 0 )
        SclRegLoadUnloadHive(0, v7, 0);
      else
        v8 = SclRegLoadUnloadHive(0, v7, 0);
    }
  }
  SclEtwWriteString(v2, (__int64)SclEvent_ProcessRegistryHive_Stop, (__int64)a2);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b738  mov     r11, rsp
0x18000b73b  mov     [r11+10h], rbx
0x18000b73f  mov     [r11+18h], rbp
0x18000b743  push    rsi
0x18000b744  push    rdi
0x18000b745  push    r12
0x18000b747  push    r14
0x18000b749  push    r15
0x18000b74b  sub     rsp, 40h
0x18000b74f  xor     eax, eax
0x18000b751  mov     [r11-38h], rdx
0x18000b755  lea     r12, [rcx+480h]
0x18000b75c  mov     qword ptr [r11+8], 0
0x18000b764  test    rcx, rcx
0x18000b767  lea     r8, SclEvent_Generic_Info
0x18000b76e  mov     rsi, rdx
0x18000b771  mov     r15, rcx
0x18000b774  mov     r14, r12
0x18000b777  mov     r9d, 6F6h
0x18000b77d  cmovz   r14, rax
0x18000b781  mov     edx, 1
0x18000b786  lea     rax, aProcessingProf; "Processing profile hive: [%ws]"
0x18000b78d  mov     rcx, r14
0x18000b790  mov     [r11-40h], rax
0x18000b794  lea     rax, aSclregprocessp; "SclRegProcessProfileHive"
0x18000b79b  mov     [r11-48h], rax
0x18000b79f  call    SclLogGenericMessage
0x18000b7a4  mov     r8, rsi
0x18000b7a7  lea     rdx, SclEvent_ProcessRegistryHive_Start
0x18000b7ae  mov     rcx, r12
0x18000b7b1  call    SclEtwWriteString
0x18000b7b6  lea     rdx, [rsp+68h+P]
0x18000b7bb  mov     rcx, rsi
0x18000b7be  call    SclRegGetCanonicalMountKeyPath
0x18000b7c3  mov     rdi, [rsp+68h+P]
0x18000b7c8  mov     ebx, eax
0x18000b7ca  test    eax, eax
0x18000b7cc  js      loc_18000B8BB
0x18000b7d2  mov     r8, rsi
0x18000b7d5  mov     rdx, rdi
0x18000b7d8  mov     cl, 1
0x18000b7da  call    SclRegLoadUnloadHive
0x18000b7df  mov     ebp, eax
0x18000b7e1  mov     ebx, eax
0x18000b7e3  shr     ebp, 1Fh
0x18000b7e6  xor     bpl, 1
0x18000b7ea  cmp     eax, 0C0000043h
0x18000b7ef  jnz     short loc_18000B849
0x18000b7f1  lea     rdx, [rsp+68h+P]
0x18000b7f6  mov     rcx, rsi
0x18000b7f9  call    SclRegFindLoadedHive
0x18000b7fe  mov     rdi, [rsp+68h+P]
0x18000b803  test    eax, eax
0x18000b805  js      loc_18000B89C
0x18000b80b  mov     [rsp+68h+var_30], rdi
0x18000b810  lea     rax, aFoundHiveWsAlr; "Found hive [%ws] already loaded at: [%w"...
0x18000b817  mov     [rsp+68h+var_38], rsi
0x18000b81c  lea     r8, SclEvent_Generic_Info
0x18000b823  mov     [rsp+68h+var_40], rax
0x18000b828  mov     r9d, 71Ah
0x18000b82e  lea     rax, aSclregprocessp; "SclRegProcessProfileHive"
0x18000b835  mov     edx, 1
0x18000b83a  mov     rcx, r14
0x18000b83d  mov     [rsp+68h+var_48], rax
0x18000b842  call    SclLogGenericMessage
0x18000b847  jmp     short loc_18000B84D
0x18000b849  test    eax, eax
0x18000b84b  js      short loc_18000B89C
0x18000b84d  xor     r8d, r8d
0x18000b850  mov     rdx, rdi
0x18000b853  mov     rcx, r15
0x18000b856  call    SclRegProcessKey
0x18000b85b  mov     ebx, eax
0x18000b85d  test    eax, eax
0x18000b85f  jns     short loc_18000B89C
0x18000b861  mov     [rsp+68h+var_30], rsi
0x18000b866  lea     r8, SclEvent_Generic_Error
0x18000b86d  mov     dword ptr [rsp+68h+var_38], eax
0x18000b871  mov     r9d, 727h
0x18000b877  lea     rax, aLxFailedToProc_3; "(%lx): Failed to process user hive [%ws"...
0x18000b87e  mov     edx, 3
0x18000b883  mov     [rsp+68h+var_40], rax
0x18000b888  mov     rcx, r14
0x18000b88b  lea     rax, aSclregprocessp; "SclRegProcessProfileHive"
0x18000b892  mov     [rsp+68h+var_48], rax
0x18000b897  call    SclLogGenericMessage
0x18000b89c  test    bpl, bpl
0x18000b89f  jz      short loc_18000B8BB
0x18000b8a1  xor     r8d, r8d
0x18000b8a4  xor     ecx, ecx
0x18000b8a6  mov     rdx, rdi
0x18000b8a9  test    ebx, ebx
0x18000b8ab  js      short loc_18000B8B6
0x18000b8ad  call    SclRegLoadUnloadHive
0x18000b8b2  mov     ebx, eax
0x18000b8b4  jmp     short loc_18000B8BB
0x18000b8b6  call    SclRegLoadUnloadHive
0x18000b8bb  mov     r8, rsi
0x18000b8be  lea     rdx, SclEvent_ProcessRegistryHive_Stop
0x18000b8c5  mov     rcx, r12
0x18000b8c8  call    SclEtwWriteString
0x18000b8cd  test    rdi, rdi
0x18000b8d0  jz      short loc_18000B8EA
0x18000b8d2  mov     rcx, gs:60h
0x18000b8db  mov     r8, rdi; P
0x18000b8de  xor     edx, edx; Flags
0x18000b8e0  mov     rcx, [rcx+30h]; HeapHandle
0x18000b8e4  call    cs:__imp_RtlFreeHeap
0x18000b8ea  lea     r11, [rsp+68h+var_28]
0x18000b8ef  mov     eax, ebx
0x18000b8f1  mov     rbx, [r11+38h]
0x18000b8f5  mov     rbp, [r11+40h]
0x18000b8f9  mov     rsp, r11
0x18000b8fc  pop     r15
0x18000b8fe  pop     r14
0x18000b900  pop     r12
0x18000b902  pop     rdi
0x18000b903  pop     rsi
0x18000b904  retn
```
