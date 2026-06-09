# VerifyChunk(FileView const &)

- ea: `0x180033de0`
- end: `0x180033f2b`
- name: `?VerifyChunk@@YA_NAEBVFileView@@@Z`
- size: `331`
- prototype: `bool __fastcall(const struct FileView *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032704`
- `0x1800340a8`
- `0x18003459c`

## callees

- `0x180029294`
- `0x180033b4c`
- `0x180033cb0`
- `0x180033de0`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180033eb5`
- `ntdll!RtlComputeCrc32` at `0x180033eb5`

## pseudocode

```c
char __fastcall VerifyChunk(const struct FileView *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  LastErrInfo *v5; // rcx
  __int64 v6; // rdx
  ULONG v7; // eax
  __int64 v8; // r8

  if ( IsChunkHeaderValid(*(const struct ChunkHeader **)a1) )
  {
    if ( (unsigned int)(*(_DWORD *)(v3 + 48) - 512) > 0xFE00 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v6 = 19;
    }
    else
    {
      if ( (*(_BYTE *)(v3 + 120) & 4) != 0 )
        return 1;
      v7 = CalcGeneralHeaderCRC((PUCHAR)v3, v2, v4, 512);
      v8 = *(_QWORD *)a1;
      if ( v7 != *(_DWORD *)(*(_QWORD *)a1 + 124LL) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          return 0;
        }
        v6 = 20;
        goto LABEL_24;
      }
      if ( *(_QWORD *)(v8 + 16) == -1
        || *(_DWORD *)(*(_QWORD *)a1 + 52LL) == RtlComputeCrc32(
                                                  0,
                                                  (PUCHAR)(*((_QWORD *)a1 + 2) + 512LL),
                                                  *(_DWORD *)(v8 + 48) - 512) )
      {
        return 1;
      }
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 0;
      }
      v6 = 21;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LastErrInfo *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 0;
    }
    v6 = 18;
  }
LABEL_24:
  WPP_SF_(*((_QWORD *)v5 + 2), v6, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180033de0  push    rbx
0x180033de2  sub     rsp, 20h
0x180033de6  mov     rbx, rcx
0x180033de9  mov     rcx, [rcx]; struct ChunkHeader *
0x180033dec  call    ?IsChunkHeaderValid@@YA_NPEBUChunkHeader@@@Z; IsChunkHeaderValid(ChunkHeader const *)
0x180033df1  test    al, al
0x180033df3  jnz     short loc_180033E2D
0x180033df5  mov     rcx, cs:WPP_GLOBAL_Control
0x180033dfc  lea     rax, WPP_GLOBAL_Control
0x180033e03  cmp     rcx, rax
0x180033e06  jz      loc_180033F23
0x180033e0c  test    dword ptr [rcx+1Ch], 8000h
0x180033e13  jz      loc_180033F23
0x180033e19  cmp     byte ptr [rcx+19h], 4
0x180033e1d  jb      loc_180033F23
0x180033e23  mov     edx, 12h
0x180033e28  jmp     loc_180033F13
0x180033e2d  mov     eax, [rcx+30h]
0x180033e30  mov     r9d, 200h; unsigned int
0x180033e36  sub     eax, r9d
0x180033e39  cmp     eax, 0FE00h
0x180033e3e  ja      loc_180033EEC
0x180033e44  test    byte ptr [rcx+78h], 4
0x180033e48  jnz     short loc_180033E97
0x180033e4a  call    ?CalcGeneralHeaderCRC@@YAKPEBEKKK@Z; CalcGeneralHeaderCRC(uchar const *,ulong,ulong,ulong)
0x180033e4f  mov     r8, [rbx]
0x180033e52  cmp     eax, [r8+7Ch]
0x180033e56  jz      short loc_180033E90
0x180033e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180033e5f  lea     rax, WPP_GLOBAL_Control
0x180033e66  cmp     rcx, rax
0x180033e69  jz      loc_180033F23
0x180033e6f  test    dword ptr [rcx+1Ch], 8000h
0x180033e76  jz      loc_180033F23
0x180033e7c  cmp     byte ptr [rcx+19h], 4
0x180033e80  jb      loc_180033F23
0x180033e86  mov     edx, 14h
0x180033e8b  jmp     loc_180033F13
0x180033e90  cmp     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFFh
0x180033e95  jnz     short loc_180033E9E
0x180033e97  mov     al, 1
0x180033e99  jmp     loc_180033F25
0x180033e9e  mov     rax, [rbx+10h]
0x180033ea2  xor     ecx, ecx; InitialCrc
0x180033ea4  mov     r8d, [r8+30h]
0x180033ea8  lea     rdx, [rax+200h]; Buffer
0x180033eaf  sub     r8d, edx
0x180033eb2  add     r8d, eax; Length
0x180033eb5  call    cs:__imp_RtlComputeCrc32
0x180033ebb  mov     rcx, [rbx]
0x180033ebe  cmp     [rcx+34h], eax
0x180033ec1  jz      short loc_180033E97
0x180033ec3  mov     rcx, cs:WPP_GLOBAL_Control
0x180033eca  lea     rax, WPP_GLOBAL_Control
0x180033ed1  cmp     rcx, rax
0x180033ed4  jz      short loc_180033F23
0x180033ed6  test    dword ptr [rcx+1Ch], 8000h
0x180033edd  jz      short loc_180033F23
0x180033edf  cmp     byte ptr [rcx+19h], 4
0x180033ee3  jb      short loc_180033F23
0x180033ee5  mov     edx, 15h
0x180033eea  jmp     short loc_180033F13
0x180033eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180033ef3  lea     rax, WPP_GLOBAL_Control
0x180033efa  cmp     rcx, rax
0x180033efd  jz      short loc_180033F23
0x180033eff  test    dword ptr [rcx+1Ch], 8000h
0x180033f06  jz      short loc_180033F23
0x180033f08  cmp     byte ptr [rcx+19h], 4
0x180033f0c  jb      short loc_180033F23
0x180033f0e  mov     edx, 13h
0x180033f13  mov     rcx, [rcx+10h]
0x180033f17  lea     r8, WPP_d678aa4655f1354a2fe0a66ad85eee91_Traceguids
0x180033f1e  call    WPP_SF_
0x180033f23  xor     al, al
0x180033f25  add     rsp, 20h
0x180033f29  pop     rbx
0x180033f2a  retn
```
