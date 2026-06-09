# GetProductKeyTypeFromRegistry

- ea: `0x18003b878`
- end: `0x18003b943`
- name: `GetProductKeyTypeFromRegistry`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800056d0`
- `0x180019170`

## callees

- `0x180003520`
- `0x180004288`
- `0x18003af34`
- `0x18003b294`
- `0x18003b878`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b912`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b926`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b912`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b926`

## pseudocode

```c
__int64 __fastcall GetProductKeyTypeFromRegistry(_QWORD *a1)
{
  void *v1; // rbx
  void *v2; // rdi
  unsigned int v4; // esi
  int Pid4FromRegistryInternal; // eax
  int v6; // eax
  void *v8; // [rsp+40h] [rbp+8h] BYREF
  char *v9; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 0;
  v9 = 0;
  v8 = 0;
  if ( a1 )
  {
    Pid4FromRegistryInternal = GetPid4FromRegistryInternal(&v9);
    v4 = Pid4FromRegistryInternal;
    if ( Pid4FromRegistryInternal >= 0 )
    {
      v1 = v9;
      v6 = CMiscHelpersT<CEmptyType>::AssignString(v9 + 1016, &v8, 128);
      v4 = v6;
      if ( v6 >= 0 )
      {
        *a1 = v8;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
        v2 = v8;
      }
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Pid4FromRegistryInternal);
      v1 = v9;
    }
  }
  else
  {
    v4 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( v2 )
    LocalFree(v2);
  if ( v1 )
    LocalFree(v1);
  return v4;
}

```

## disassembly

```asm
0x18003b878  mov     rax, rsp
0x18003b87b  mov     [rax+18h], rbx
0x18003b87f  mov     [rax+10h], rdx
0x18003b883  push    rsi
0x18003b884  push    rdi
0x18003b885  push    r14
0x18003b887  sub     rsp, 20h
0x18003b88b  xor     ebx, ebx
0x18003b88d  xor     edi, edi
0x18003b88f  mov     [rax+10h], rbx
0x18003b893  mov     r14, rcx
0x18003b896  mov     [rax+8], rdi
0x18003b89a  test    rcx, rcx
0x18003b89d  jnz     short loc_18003B8AD
0x18003b89f  mov     esi, 80070057h
0x18003b8a4  mov     ecx, esi
0x18003b8a6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b8ab  jmp     short loc_18003B903
0x18003b8ad  lea     rcx, [rsp+38h+arg_8]
0x18003b8b2  call    GetPid4FromRegistryInternal
0x18003b8b7  mov     esi, eax
0x18003b8b9  test    eax, eax
0x18003b8bb  jns     short loc_18003B8CB
0x18003b8bd  mov     ecx, eax
0x18003b8bf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b8c4  mov     rbx, [rsp+38h+arg_8]
0x18003b8c9  jmp     short loc_18003B903
0x18003b8cb  mov     rbx, [rsp+38h+arg_8]
0x18003b8d0  lea     rdx, [rsp+38h+arg_0]
0x18003b8d5  mov     r8d, 80h
0x18003b8db  lea     rcx, [rbx+3F8h]
0x18003b8e2  call    ?AssignString@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAGI@Z; CMiscHelpersT<CEmptyType>::AssignString(ushort const *,ushort * *,uint)
0x18003b8e7  mov     esi, eax
0x18003b8e9  test    eax, eax
0x18003b8eb  jns     short loc_18003B8FB
0x18003b8ed  mov     ecx, eax
0x18003b8ef  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b8f4  mov     rdi, [rsp+38h+arg_0]
0x18003b8f9  jmp     short loc_18003B903
0x18003b8fb  mov     rax, [rsp+38h+arg_0]
0x18003b900  mov     [r14], rax
0x18003b903  mov     ecx, esi
0x18003b905  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b90a  test    rdi, rdi
0x18003b90d  jz      short loc_18003B91E
0x18003b90f  mov     rcx, rdi; hMem
0x18003b912  call    cs:__imp_LocalFree
0x18003b919  nop     dword ptr [rax+rax+00h]
0x18003b91e  test    rbx, rbx
0x18003b921  jz      short loc_18003B932
0x18003b923  mov     rcx, rbx; hMem
0x18003b926  call    cs:__imp_LocalFree
0x18003b92d  nop     dword ptr [rax+rax+00h]
0x18003b932  mov     rbx, [rsp+38h+arg_10]
0x18003b937  mov     eax, esi
0x18003b939  add     rsp, 20h
0x18003b93d  pop     r14
0x18003b93f  pop     rdi
0x18003b940  pop     rsi
0x18003b941  retn
```
