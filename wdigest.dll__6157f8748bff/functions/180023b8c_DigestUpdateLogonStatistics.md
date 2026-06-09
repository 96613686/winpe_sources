# DigestUpdateLogonStatistics

- ea: `0x180023b8c`
- end: `0x180023c19`
- name: `DigestUpdateLogonStatistics`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001d5e8`

## callees

- `0x180011fec`
- `0x1800185b8`
- `0x180023b8c`

## import_xrefs

- `SAMSRV!SamIUpdateLogonStatistics` at `0x180023bd5`
- `SAMSRV!SamIUpdateLogonStatistics` at `0x180023bd5`

## pseudocode

```c
__int64 __fastcall DigestUpdateLogonStatistics(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids);
  v4 = SamIUpdateLogonStatistics(a1, a2);
  v5 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids, v4);
  return v5;
}

```

## disassembly

```asm
0x180023b8c  mov     [rsp+arg_0], rbx
0x180023b91  mov     [rsp+arg_8], rsi
0x180023b96  push    rdi
0x180023b97  sub     rsp, 20h
0x180023b9b  mov     rbx, rdx
0x180023b9e  mov     rdi, rcx
0x180023ba1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ba8  lea     rsi, WPP_GLOBAL_Control
0x180023baf  cmp     rcx, rsi
0x180023bb2  jz      short loc_180023BCF
0x180023bb4  test    byte ptr [rcx+1Ch], 80h
0x180023bb8  jz      short loc_180023BCF
0x180023bba  mov     rcx, [rcx+10h]
0x180023bbe  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023bc5  mov     edx, 37h ; '7'
0x180023bca  call    WPP_SF_
0x180023bcf  mov     rdx, rbx
0x180023bd2  mov     rcx, rdi
0x180023bd5  call    cs:__imp_SamIUpdateLogonStatistics
0x180023bdb  mov     ebx, eax
0x180023bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180023be4  cmp     rcx, rsi
0x180023be7  jz      short loc_180023C07
0x180023be9  test    byte ptr [rcx+1Ch], 80h
0x180023bed  jz      short loc_180023C07
0x180023bef  mov     rcx, [rcx+10h]
0x180023bf3  lea     r8, WPP_786c13e3ce4938baeda573cf038ab08e_Traceguids
0x180023bfa  mov     edx, 38h ; '8'
0x180023bff  mov     r9d, eax
0x180023c02  call    WPP_SF_d
0x180023c07  mov     rsi, [rsp+28h+arg_8]
0x180023c0c  mov     eax, ebx
0x180023c0e  mov     rbx, [rsp+28h+arg_0]
0x180023c13  add     rsp, 20h
0x180023c17  pop     rdi
0x180023c18  retn
```
