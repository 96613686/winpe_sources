# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::InsertOrReplace(wchar_t *,Wsp::Health::CHealthConnection *)

- ea: `0x18007b910`
- end: `0x18007b98a`
- name: `?InsertOrReplace@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAAJPEA_WPEAVCHealthConnection@Health@Wsp@@@Z`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18007b8b0`

## callees

- `0x18007b910`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007b933`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007b933`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18007b953`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18007b953`

## pseudocode

```c
__int64 __fastcall CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::InsertOrReplace(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int8 NewElement; // [rsp+40h] [rbp+8h] BYREF

  Buffer[0] = a2;
  Buffer[1] = a3;
  NewElement = 0;
  RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), Buffer);
  if ( !RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), Buffer, 0x10u, &NewElement) )
    return 2147942414LL;
  if ( !NewElement )
    return 2147942583LL;
  ++*(_DWORD *)(a1 + 112);
  return 0;
}

```

## disassembly

```asm
0x18007b910  mov     rax, rsp
0x18007b913  mov     [rax+10h], rbx
0x18007b917  push    rdi
0x18007b918  sub     rsp, 30h
0x18007b91c  mov     rdi, rcx
0x18007b91f  mov     [rax-18h], rdx
0x18007b923  lea     rdx, [rax-18h]; Buffer
0x18007b927  mov     [rax-10h], r8
0x18007b92b  add     rcx, 8; Table
0x18007b92f  mov     byte ptr [rax+8], 0
0x18007b933  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18007b93a  nop     dword ptr [rax+rax+00h]
0x18007b93f  lea     r9, [rsp+38h+NewElement]; NewElement
0x18007b944  mov     r8d, 10h; BufferSize
0x18007b94a  lea     rdx, [rsp+38h+Buffer]; Buffer
0x18007b94f  lea     rcx, [rdi+8]; Table
0x18007b953  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18007b95a  nop     dword ptr [rax+rax+00h]
0x18007b95f  test    rax, rax
0x18007b962  jnz     short loc_18007B96B
0x18007b964  mov     eax, 8007000Eh
0x18007b969  jmp     short loc_18007B97E
0x18007b96b  cmp     [rsp+38h+NewElement], 0
0x18007b970  jz      short loc_18007B979
0x18007b972  inc     dword ptr [rdi+70h]
0x18007b975  xor     eax, eax
0x18007b977  jmp     short loc_18007B97E
0x18007b979  mov     eax, 800700B7h
0x18007b97e  mov     rbx, [rsp+38h+arg_8]
0x18007b983  add     rsp, 30h
0x18007b987  pop     rdi
0x18007b988  retn
```
