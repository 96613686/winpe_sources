# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::InsertOrReplace(wchar_t *,Wsp::Health::CHealthConnection *)

- ea: `0x180070510`
- end: `0x18007057d`
- name: `?InsertOrReplace@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAAJPEA_WPEAVCHealthConnection@Health@Wsp@@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800704b0`

## callees

- `0x180070510`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180070533`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180070533`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18007054d`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18007054d`

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
0x180070510  mov     rax, rsp
0x180070513  mov     [rax+10h], rbx
0x180070517  push    rdi
0x180070518  sub     rsp, 30h
0x18007051c  mov     rdi, rcx
0x18007051f  mov     [rax-18h], rdx
0x180070523  lea     rdx, [rax-18h]; Buffer
0x180070527  mov     [rax-10h], r8
0x18007052b  add     rcx, 8; Table
0x18007052f  mov     byte ptr [rax+8], 0
0x180070533  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180070539  lea     r9, [rsp+38h+NewElement]; NewElement
0x18007053e  mov     r8d, 10h; BufferSize
0x180070544  lea     rdx, [rsp+38h+Buffer]; Buffer
0x180070549  lea     rcx, [rdi+8]; Table
0x18007054d  call    cs:__imp_RtlInsertElementGenericTableAvl
0x180070553  test    rax, rax
0x180070556  jnz     short loc_18007055F
0x180070558  mov     eax, 8007000Eh
0x18007055d  jmp     short loc_180070572
0x18007055f  cmp     [rsp+38h+NewElement], 0
0x180070564  jz      short loc_18007056D
0x180070566  inc     dword ptr [rdi+70h]
0x180070569  xor     eax, eax
0x18007056b  jmp     short loc_180070572
0x18007056d  mov     eax, 800700B7h
0x180070572  mov     rbx, [rsp+38h+arg_8]
0x180070577  add     rsp, 30h
0x18007057b  pop     rdi
0x18007057c  retn
```
