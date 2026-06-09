# HUBCONNECTOR_GetCompanionPort

- ea: `0x140083b00`
- end: `0x140083c7e`
- name: `HUBCONNECTOR_GetCompanionPort`
- size: `382`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400330f4`
- `0x14007d144`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x140045570`
- `0x140083b00`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140083bac`
- `ntoskrnl!RtlCompareMemory` at `0x140083bac`

## pseudocode

```c
__int64 __fastcall HUBCONNECTOR_GetCompanionPort(__int64 a1, int a2)
{
  __int64 v2; // rdi
  int v3; // ebp
  int v5; // eax
  int v6; // r9d
  __int64 v7; // rcx
  _QWORD *v8; // r14
  _QWORD *i; // rax
  _QWORD *v10; // rbx
  int v12; // ecx
  bool v13; // zf
  int v14; // [rsp+28h] [rbp-40h]

  v2 = 0;
  v3 = (unsigned __int16)a2;
  if ( (*(_DWORD *)(a1 + 204) & 0x20) != 0 )
  {
    if ( (unsigned __int16)a2 <= 1u )
    {
      v8 = (_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015
                                                                                               + 1616))(
                        WdfDriverGlobals,
                        WdfDriverGlobals->Driver,
                        off_14006B2C0)
                    + 40);
      for ( i = (_QWORD *)*v8; ; i = (_QWORD *)v10[10] )
      {
        v10 = i - 10;
        if ( v8 == i )
          goto LABEL_10;
        if ( RtlCompareMemory(i - 10, (const void *)(a1 + 1368), 0x38u) == 56 )
          break;
      }
      if ( !v10 )
      {
LABEL_10:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1432), a2, 4, 22, (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids);
        }
        return v2;
      }
      v12 = *(_DWORD *)(a1 + 208);
      if ( v12 == 512 )
      {
        if ( !v3 )
          return v10[8];
        v13 = v3 == 1;
      }
      else
      {
        if ( v12 != 768 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v2;
          v14 = *(_DWORD *)(a1 + 208);
          v6 = 23;
          v7 = *(_QWORD *)(a1 + 1432);
          goto LABEL_5;
        }
        if ( !v3 )
          return v10[7];
        v2 = v10[8];
        v13 = a1 == v2;
      }
      if ( v13 )
        return v10[9];
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = *(_DWORD *)(a1 + 208);
      v6 = 21;
      v7 = *(_QWORD *)(a1 + 1432);
      v14 = v5;
LABEL_5:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(v7, (_WORD)a2, 6, v6, (__int64)WPP_e747a75ab0a43332580ac19f3a627527_Traceguids, v14);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140083b00  push    rbx
0x140083b02  push    rbp
0x140083b03  push    rsi
0x140083b04  push    rdi
0x140083b05  push    r14
0x140083b07  push    r15
0x140083b09  sub     rsp, 38h
0x140083b0d  mov     eax, [rcx+0CCh]
0x140083b13  xor     edi, edi
0x140083b15  movzx   ebp, dx
0x140083b18  mov     rsi, rcx
0x140083b1b  test    al, 20h
0x140083b1d  jz      loc_140083BFF
0x140083b23  cmp     ebp, 1
0x140083b26  jbe     short loc_140083B6F
0x140083b28  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083b2f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083b36  jz      loc_140083BFF
0x140083b3c  mov     eax, [rcx+0D0h]
0x140083b42  lea     r9d, [rdi+15h]
0x140083b46  mov     rcx, [rcx+598h]
0x140083b4d  mov     [rsp+68h+var_40], eax
0x140083b51  lea     rax, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140083b58  mov     dl, 2
0x140083b5a  mov     r8d, 6
0x140083b60  mov     [rsp+68h+var_48], rax
0x140083b65  call    WPP_RECORDER_SF_d
0x140083b6a  jmp     loc_140083BFF
0x140083b6f  mov     rax, cs:WdfFunctions_01015
0x140083b76  mov     rcx, cs:WdfDriverGlobals
0x140083b7d  mov     r8, cs:off_14006B2C0
0x140083b84  mov     rax, [rax+650h]
0x140083b8b  mov     rdx, [rcx]
0x140083b8e  call    _guard_dispatch_icall
0x140083b93  lea     r14, [rax+28h]
0x140083b97  mov     rax, [r14]
0x140083b9a  jmp     short loc_140083BC2
0x140083b9c  mov     r8d, 38h ; '8'; Length
0x140083ba2  lea     rdx, [rsi+558h]; Source2
0x140083ba9  mov     rcx, rbx; Source1
0x140083bac  call    cs:__imp_RtlCompareMemory
0x140083bb3  nop     dword ptr [rax+rax+00h]
0x140083bb8  cmp     rax, 38h ; '8'
0x140083bbc  jz      short loc_140083C10
0x140083bbe  mov     rax, [rbx+50h]
0x140083bc2  lea     rbx, [rax-50h]
0x140083bc6  cmp     r14, rax
0x140083bc9  jnz     short loc_140083B9C
0x140083bcb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083bd2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083bd9  jz      short loc_140083BFF
0x140083bdb  mov     rcx, [rsi+598h]
0x140083be2  lea     rax, WPP_e747a75ab0a43332580ac19f3a627527_Traceguids
0x140083be9  mov     r9d, 16h
0x140083bef  mov     [rsp+68h+var_48], rax
0x140083bf4  mov     dl, 2
0x140083bf6  lea     r8d, [r9-12h]
0x140083bfa  call    WPP_RECORDER_SF_
0x140083bff  mov     rax, rdi
0x140083c02  add     rsp, 38h
0x140083c06  pop     r15
0x140083c08  pop     r14
0x140083c0a  pop     rdi
0x140083c0b  pop     rsi
0x140083c0c  pop     rbp
0x140083c0d  pop     rbx
0x140083c0e  retn
0x140083c10  test    rbx, rbx
0x140083c13  jz      short loc_140083BCB
0x140083c15  mov     ecx, [rsi+0D0h]
0x140083c1b  cmp     ecx, 200h
0x140083c21  jz      short loc_140083C69
0x140083c23  cmp     ecx, 300h
0x140083c29  jz      short loc_140083C51
0x140083c2b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140083c32  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083c39  jz      short loc_140083BFF
0x140083c3b  mov     [rsp+68h+var_40], ecx
0x140083c3f  mov     r9d, 17h
0x140083c45  mov     rcx, [rsi+598h]
0x140083c4c  jmp     loc_140083B51
0x140083c51  test    ebp, ebp
0x140083c53  jz      short loc_140083C63
0x140083c55  cmp     ebp, 1
0x140083c58  jnz     short loc_140083BFF
0x140083c5a  mov     rdi, [rbx+40h]
0x140083c5e  cmp     rsi, rdi
0x140083c61  jmp     short loc_140083C70
0x140083c63  mov     rdi, [rbx+38h]
0x140083c67  jmp     short loc_140083BFF
0x140083c69  test    ebp, ebp
0x140083c6b  jz      short loc_140083C78
0x140083c6d  cmp     ebp, 1
0x140083c70  jnz     short loc_140083BFF
0x140083c72  mov     rdi, [rbx+48h]
0x140083c76  jmp     short loc_140083BFF
0x140083c78  mov     rdi, [rbx+40h]
0x140083c7c  jmp     short loc_140083BFF
```
