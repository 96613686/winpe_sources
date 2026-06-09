# SampIsValidClientHandle(void *,void * *)

- ea: `0x180003220`
- end: `0x180003365`
- name: `?SampIsValidClientHandle@@YAEPEAXPEAPEAX@Z`
- size: `325`
- prototype: `unsigned __int8 __fastcall(void *, void **)`
- caller_count: `56`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800011f0`
- `0x180001450`
- `0x180001800`
- `0x180001a30`
- `0x180001c50`
- `0x180001ea0`
- `0x180002110`
- `0x180002390`
- `0x180002530`
- `0x180002870`
- `0x180002a80`
- `0x180002e90`
- `0x1800033c0`
- `0x180003a00`
- `0x1800040e0`
- `0x18000ad50`
- `0x18000c650`
- `0x18000c850`
- `0x18000ca60`
- `0x18000ccb0`
- `0x18000d330`
- `0x18000d630`
- `0x18000d930`
- `0x18000dde0`
- `0x18000e0e0`
- `0x18000e2e0`
- `0x18000e4e0`
- `0x18000e6e0`
- `0x18000e9c0`
- `0x18000eca0`
- `0x18000ef50`
- `0x18000f210`
- `0x18000f5c0`
- `0x18000fed0`
- `0x180010170`
- `0x180010410`
- `0x180010830`
- `0x180010a40`
- `0x180010e70`
- `0x1800110c0`
- `0x1800112c0`
- `0x1800114c0`
- `0x1800116c0`
- `0x180011910`
- `0x180011aa0`
- `0x180011cb0`
- `0x180011ec0`
- `0x1800120d0`
- `0x1800123b0`
- `0x180012c30`

## callees

- `0x180003220`
- `0x1800078c0`
- `0x180014a50`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180003268`
- `ntdll!RtlValidSid` at `0x180003268`

## pseudocode

```c
__int64 __fastcall SampIsValidClientHandle(void **a1, void **a2)
{
  unsigned __int8 v4; // di
  void *v5; // rsi
  void *v6; // rcx

  v4 = 1;
  if ( a1 )
  {
    v5 = *a1;
    if ( !*a1 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
      v4 = 0;
    }
    v6 = a1[2];
    if ( v6 && !RtlValidSid(v6) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
      v4 = 0;
    }
    if ( v4 && a2 )
      *a2 = v5;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_02389d7df6583a073e538dcda8c3a574_Traceguids);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180003220  mov     [rsp+arg_10], rbx
0x180003225  mov     [rsp+arg_8], rdx
0x18000322a  mov     [rsp+arg_0], rcx
0x18000322f  push    rsi
0x180003230  push    rdi
0x180003231  push    r14
0x180003233  sub     rsp, 30h
0x180003237  mov     r14, rdx
0x18000323a  mov     rbx, rcx
0x18000323d  mov     dil, 1
0x180003240  mov     [rsp+48h+var_20], 0
0x180003249  test    rcx, rcx
0x18000324c  jz      loc_180003338
0x180003252  mov     rsi, [rcx]
0x180003255  mov     [rsp+48h+var_20], rsi
0x18000325a  test    rsi, rsi
0x18000325d  jz      short loc_1800032A4
0x18000325f  mov     rcx, [rbx+10h]; Sid
0x180003263  test    rcx, rcx
0x180003266  jz      short loc_1800032D6
0x180003268  call    cs:__imp_RtlValidSid
0x18000326e  test    al, al
0x180003270  jnz     short loc_1800032D6
0x180003272  mov     rcx, cs:WPP_GLOBAL_Control
0x180003279  test    byte ptr [rcx+1Ch], 2
0x18000327d  jz      short loc_18000329A
0x18000327f  cmp     byte ptr [rcx+19h], 2
0x180003283  jb      short loc_18000329A
0x180003285  mov     edx, 30h ; '0'
0x18000328a  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180003291  mov     rcx, [rcx+10h]
0x180003295  call    WPP_SF_
0x18000329a  xor     dil, dil
0x18000329d  mov     [rsp+48h+var_28], dil
0x1800032a2  jmp     short loc_1800032D6
0x1800032a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032ab  test    byte ptr [rcx+1Ch], 2
0x1800032af  jz      short loc_1800032CC
0x1800032b1  cmp     byte ptr [rcx+19h], 2
0x1800032b5  jb      short loc_1800032CC
0x1800032b7  mov     edx, 2Fh ; '/'
0x1800032bc  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800032c3  mov     rcx, [rcx+10h]
0x1800032c7  call    WPP_SF_
0x1800032cc  xor     dil, dil
0x1800032cf  mov     [rsp+48h+var_28], dil
0x1800032d4  jmp     short loc_18000325F
0x1800032d6  jmp     short loc_180003317
0x1800032d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032df  test    byte ptr [rcx+1Ch], 2
0x1800032e3  jz      short loc_180003305
0x1800032e5  cmp     byte ptr [rcx+19h], 2
0x1800032e9  jb      short loc_180003305
0x1800032eb  mov     edx, 31h ; '1'
0x1800032f0  mov     r9, [rsp+48h+arg_0]
0x1800032f5  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x1800032fc  mov     rcx, [rcx+10h]
0x180003300  call    WPP_SF_q
0x180003305  xor     dil, dil
0x180003308  mov     [rsp+48h+var_28], dil
0x18000330d  mov     r14, [rsp+48h+arg_8]
0x180003312  mov     rsi, [rsp+48h+var_20]
0x180003317  test    dil, dil
0x18000331a  jnz     short loc_18000332E
0x18000331c  movzx   eax, dil
0x180003320  mov     rbx, [rsp+48h+arg_10]
0x180003325  add     rsp, 30h
0x180003329  pop     r14
0x18000332b  pop     rdi
0x18000332c  pop     rsi
0x18000332d  retn
0x18000332e  test    r14, r14
0x180003331  jz      short loc_18000331C
0x180003333  mov     [r14], rsi
0x180003336  jmp     short loc_18000331C
0x180003338  mov     rcx, cs:WPP_GLOBAL_Control
0x18000333f  test    byte ptr [rcx+1Ch], 2
0x180003343  jz      short loc_180003360
0x180003345  cmp     byte ptr [rcx+19h], 2
0x180003349  jb      short loc_180003360
0x18000334b  mov     edx, 2Eh ; '.'
0x180003350  lea     r8, WPP_02389d7df6583a073e538dcda8c3a574_Traceguids
0x180003357  mov     rcx, [rcx+10h]
0x18000335b  call    WPP_SF_
0x180003360  xor     dil, dil
0x180003363  jmp     short loc_18000331C
```
