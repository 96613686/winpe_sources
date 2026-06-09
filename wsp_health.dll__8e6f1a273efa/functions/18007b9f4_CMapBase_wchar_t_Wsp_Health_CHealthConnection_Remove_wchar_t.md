# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)

- ea: `0x18007b9f4`
- end: `0x18007ba56`
- name: `?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18007ae8c`
- `0x18007bba4`

## callees

- `0x18007b9f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ba3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ba3c`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007ba17`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18007ba17`

## pseudocode

```c
__int64 __fastcall CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(__int64 a1, __int64 a2)
{
  BOOLEAN v3; // al
  unsigned int v4; // edi
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  v6[0] = a2;
  v6[1] = 0;
  v3 = RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 8), v6);
  v4 = v3;
  if ( v3 )
    --*(_DWORD *)(a1 + 112);
  SetLastError(v3 == 0 ? 0x490 : 0);
  return v4;
}

```

## disassembly

```asm
0x18007b9f4  mov     rax, rsp
0x18007b9f7  mov     [rax+8], rbx
0x18007b9fb  push    rdi
0x18007b9fc  sub     rsp, 30h
0x18007ba00  mov     rbx, rcx
0x18007ba03  mov     [rax-18h], rdx
0x18007ba07  add     rcx, 8; Table
0x18007ba0b  mov     qword ptr [rax-10h], 0
0x18007ba13  lea     rdx, [rax-18h]; Buffer
0x18007ba17  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18007ba1e  nop     dword ptr [rax+rax+00h]
0x18007ba23  movzx   edi, al
0x18007ba26  test    al, al
0x18007ba28  jz      short loc_18007BA2D
0x18007ba2a  dec     dword ptr [rbx+70h]
0x18007ba2d  mov     cl, dil
0x18007ba30  neg     cl
0x18007ba32  sbb     ecx, ecx
0x18007ba34  not     ecx
0x18007ba36  and     ecx, 490h; dwErrCode
0x18007ba3c  call    cs:__imp_SetLastError
0x18007ba43  nop     dword ptr [rax+rax+00h]
0x18007ba48  mov     rbx, [rsp+38h+arg_0]
0x18007ba4d  mov     eax, edi
0x18007ba4f  add     rsp, 30h
0x18007ba53  pop     rdi
0x18007ba54  retn
```
