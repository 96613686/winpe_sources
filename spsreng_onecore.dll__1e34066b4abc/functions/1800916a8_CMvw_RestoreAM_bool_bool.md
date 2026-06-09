# CMvw::RestoreAM(bool,bool)

- ea: `0x1800916a8`
- end: `0x18009176e`
- name: `?RestoreAM@CMvw@@QEAAH_N0@Z`
- size: `198`
- prototype: `__int64 __fastcall(CMvw *__hidden this, bool, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000fcd0`
- `0x18008a04c`

## callees

- `0x180002aac`
- `0x1800916a8`
- `0x180091774`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800916fe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800916fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091708`

## pseudocode

```c
__int64 __fastcall CMvw::RestoreAM(const unsigned __int16 **this, char a2, char a3)
{
  unsigned int v3; // edi
  int v6; // eax

  v3 = 0;
  if ( !*((_DWORD *)this + 265) )
  {
    if ( a2 )
    {
      v3 = CMvw::RestoreAMUse((CMvw *)this, this[130]);
      if ( !v3 && a3 )
        v3 = CMvw::RestoreAMUse((CMvw *)this, this[131]);
      if ( !DeleteFileW(this[130]) && GetLastError() != 2 )
      {
        CWinHeap::Free((CWinHeap *)&g_heap, (void *)this[130]);
        this[130] = 0;
      }
    }
    else
    {
      if ( !a3 )
        goto LABEL_14;
      v3 = CMvw::RestoreAMUse((CMvw *)this, this[131]);
    }
    if ( !v3 && a3 )
    {
      v6 = 1;
LABEL_15:
      *((_DWORD *)this + 265) = v6;
      return v3;
    }
LABEL_14:
    v6 = 0;
    goto LABEL_15;
  }
  return v3;
}

```

## disassembly

```asm
0x1800916a8  mov     [rsp+arg_0], rbx
0x1800916ad  mov     [rsp+arg_8], rsi
0x1800916b2  push    rdi
0x1800916b3  sub     rsp, 20h
0x1800916b7  xor     edi, edi
0x1800916b9  mov     sil, r8b
0x1800916bc  mov     rbx, rcx
0x1800916bf  cmp     [rcx+424h], edi
0x1800916c5  jnz     loc_18009175C
0x1800916cb  test    dl, dl
0x1800916cd  jz      short loc_180091733
0x1800916cf  mov     rdx, [rcx+410h]; unsigned __int16 *
0x1800916d6  call    ?RestoreAMUse@CMvw@@AEAAHPEBG@Z; CMvw::RestoreAMUse(ushort const *)
0x1800916db  mov     edi, eax
0x1800916dd  test    eax, eax
0x1800916df  jnz     short loc_1800916F7
0x1800916e1  test    sil, sil
0x1800916e4  jz      short loc_1800916F7
0x1800916e6  mov     rdx, [rbx+418h]; unsigned __int16 *
0x1800916ed  mov     rcx, rbx; this
0x1800916f0  call    ?RestoreAMUse@CMvw@@AEAAHPEBG@Z; CMvw::RestoreAMUse(ushort const *)
0x1800916f5  mov     edi, eax
0x1800916f7  mov     rcx, [rbx+410h]; lpFileName
0x1800916fe  call    cs:__imp_DeleteFileW
0x180091704  test    eax, eax
0x180091706  jnz     short loc_180091746
0x180091708  call    cs:__imp_GetLastError
0x18009170e  cmp     eax, 2
0x180091711  jz      short loc_180091746
0x180091713  mov     rdx, [rbx+410h]; void *
0x18009171a  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x180091721  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x180091726  mov     qword ptr [rbx+410h], 0
0x180091731  jmp     short loc_180091746
0x180091733  test    sil, sil
0x180091736  jz      short loc_180091754
0x180091738  mov     rdx, [rcx+418h]; unsigned __int16 *
0x18009173f  call    ?RestoreAMUse@CMvw@@AEAAHPEBG@Z; CMvw::RestoreAMUse(ushort const *)
0x180091744  mov     edi, eax
0x180091746  test    edi, edi
0x180091748  jnz     short loc_180091754
0x18009174a  test    sil, sil
0x18009174d  jz      short loc_180091754
0x18009174f  lea     eax, [rdi+1]
0x180091752  jmp     short loc_180091756
0x180091754  xor     eax, eax
0x180091756  mov     [rbx+424h], eax
0x18009175c  mov     rbx, [rsp+28h+arg_0]
0x180091761  mov     eax, edi
0x180091763  mov     rsi, [rsp+28h+arg_8]
0x180091768  add     rsp, 20h
0x18009176c  pop     rdi
0x18009176d  retn
```
