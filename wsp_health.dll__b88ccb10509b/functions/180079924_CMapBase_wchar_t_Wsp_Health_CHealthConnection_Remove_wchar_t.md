# CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)

- ea: `0x180079924`
- end: `0x180079979`
- name: `?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180078ec8`
- `0x180079abc`

## callees

- `0x180079924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079966`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180079966`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180079947`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180079947`

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
0x180079924  mov     rax, rsp
0x180079927  mov     [rax+8], rbx
0x18007992b  push    rdi
0x18007992c  sub     rsp, 30h
0x180079930  mov     rbx, rcx
0x180079933  mov     [rax-18h], rdx
0x180079937  add     rcx, 8; Table
0x18007993b  mov     qword ptr [rax-10h], 0
0x180079943  lea     rdx, [rax-18h]; Buffer
0x180079947  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18007994d  movzx   edi, al
0x180079950  test    al, al
0x180079952  jz      short loc_180079957
0x180079954  dec     dword ptr [rbx+70h]
0x180079957  mov     cl, dil
0x18007995a  neg     cl
0x18007995c  sbb     ecx, ecx
0x18007995e  not     ecx
0x180079960  and     ecx, 490h; dwErrCode
0x180079966  call    cs:__imp_SetLastError
0x18007996c  mov     rbx, [rsp+38h+arg_0]
0x180079971  mov     eax, edi
0x180079973  add     rsp, 30h
0x180079977  pop     rdi
0x180079978  retn
```
