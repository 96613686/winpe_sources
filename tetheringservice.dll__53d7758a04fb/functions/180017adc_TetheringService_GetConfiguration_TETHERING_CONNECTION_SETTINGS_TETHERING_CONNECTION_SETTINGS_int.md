# TetheringService::GetConfiguration(_TETHERING_CONNECTION_SETTINGS *,_TETHERING_CONNECTION_SETTINGS *,int *)

- ea: `0x180017adc`
- end: `0x180017e52`
- name: `?GetConfiguration@TetheringService@@QEAAJPEAU_TETHERING_CONNECTION_SETTINGS@@0PEAH@Z`
- size: `886`
- prototype: `__int64 __fastcall(TetheringService *__hidden this, struct _TETHERING_CONNECTION_SETTINGS *, struct _TETHERING_CONNECTION_SETTINGS *, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000c950`
- `0x180014c8c`
- `0x180015cdc`

## callees

- `0x18000bf4c`
- `0x18000bf74`
- `0x180017adc`
- `0x18001c0dc`
- `0x18002b1f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017c1a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017dba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017c1a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017e13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017b34`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017b34`

## pseudocode

```c
__int64 __fastcall TetheringService::GetConfiguration(
        TetheringService *this,
        struct _TETHERING_CONNECTION_SETTINGS *a2,
        struct _TETHERING_CONNECTION_SETTINGS *a3,
        int *a4)
{
  __int64 v8; // r9
  unsigned int v9; // esi
  TetheringServiceTelemetry *v10; // rcx
  __int64 v11; // rdx
  _OWORD *SettingValueGlobalInternal; // rax
  _WORD *v13; // r9
  __int64 v14; // r8
  __int64 v15; // rcx
  _WORD *v16; // rax
  __int64 v17; // rdx
  bool v18; // zf
  _WORD *v19; // rcx
  __int64 v20; // rdx
  _WORD *v21; // rax
  _WORD *v22; // rcx
  _WORD *v23; // rcx
  _OWORD *v24; // rax

  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  TetheringService::ResetInactivityTimerIfNotSharing(this);
  if ( a2 )
  {
    SettingValueGlobalInternal = (_OWORD *)TetheringSettingsGetSettingValueGlobalInternal(6);
    if ( !SettingValueGlobalInternal )
    {
      v8 = 2198994950LL;
      v9 = -2095972346;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 171;
        goto LABEL_38;
      }
      goto LABEL_39;
    }
    *(_OWORD *)a2 = *SettingValueGlobalInternal;
    *((_OWORD *)a2 + 1) = SettingValueGlobalInternal[1];
    *((_OWORD *)a2 + 2) = SettingValueGlobalInternal[2];
    *((_OWORD *)a2 + 3) = SettingValueGlobalInternal[3];
    *((_OWORD *)a2 + 4) = SettingValueGlobalInternal[4];
    *((_OWORD *)a2 + 5) = SettingValueGlobalInternal[5];
    *((_OWORD *)a2 + 6) = SettingValueGlobalInternal[6];
    *((_OWORD *)a2 + 7) = SettingValueGlobalInternal[7];
    *((_OWORD *)a2 + 8) = SettingValueGlobalInternal[8];
    *((_OWORD *)a2 + 9) = SettingValueGlobalInternal[9];
    *((_OWORD *)a2 + 10) = SettingValueGlobalInternal[10];
    *((_OWORD *)a2 + 11) = SettingValueGlobalInternal[11];
    *((_OWORD *)a2 + 12) = SettingValueGlobalInternal[12];
    free(SettingValueGlobalInternal);
  }
  else if ( !a3 )
  {
    v8 = 2147942487LL;
    v9 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 170;
LABEL_38:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v8);
      goto LABEL_39;
    }
    goto LABEL_39;
  }
  v9 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      *a4 = *((unsigned __int8 *)this + 220);
      if ( *((_BYTE *)this + 220) )
      {
        v13 = (_WORD *)((char *)this + 12);
        v14 = 2147483646;
        *(_DWORD *)a3 = *((_DWORD *)this + 2);
        v15 = 2147483646;
        v16 = (_WORD *)((char *)a3 + 4);
        v17 = 33;
        do
        {
          if ( !v15 )
            break;
          if ( !*v13 )
            break;
          *v16++ = *v13++;
          --v15;
          --v17;
        }
        while ( v17 );
        v18 = v17 == 0;
        v19 = v16 - 1;
        v20 = 65;
        if ( !v18 )
          v19 = v16;
        v21 = (_WORD *)((char *)a3 + 70);
        *v19 = 0;
        v22 = (_WORD *)((char *)this + 78);
        do
        {
          if ( !v14 )
            break;
          if ( !*v22 )
            break;
          *v21++ = *v22++;
          --v14;
          --v20;
        }
        while ( v20 );
        v23 = v21 - 1;
        if ( v20 )
          v23 = v21;
        *v23 = 0;
        *((_DWORD *)a3 + 50) = *((_DWORD *)this + 52);
        *((_DWORD *)a3 + 51) = *((_DWORD *)this + 53);
      }
      else
      {
        v24 = (_OWORD *)TetheringSettingsGetSettingValueGlobalInternal(7);
        if ( v24 )
        {
          *(_OWORD *)a3 = *v24;
          *((_OWORD *)a3 + 1) = v24[1];
          *((_OWORD *)a3 + 2) = v24[2];
          *((_OWORD *)a3 + 3) = v24[3];
          *((_OWORD *)a3 + 4) = v24[4];
          *((_OWORD *)a3 + 5) = v24[5];
          *((_OWORD *)a3 + 6) = v24[6];
          *((_OWORD *)a3 + 7) = v24[7];
          *((_OWORD *)a3 + 8) = v24[8];
          *((_OWORD *)a3 + 9) = v24[9];
          *((_OWORD *)a3 + 10) = v24[10];
          *((_OWORD *)a3 + 11) = v24[11];
          *((_OWORD *)a3 + 12) = v24[12];
          free(v24);
        }
        else
        {
          v8 = 2198994950LL;
          v9 = -2095972346;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 173;
            goto LABEL_38;
          }
        }
      }
    }
    else
    {
      v8 = 2147942487LL;
      v9 = -2147024809;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 172;
        goto LABEL_38;
      }
    }
  }
LABEL_39:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x180017adc  push    rbx
0x180017ade  push    rbp
0x180017adf  push    rsi
0x180017ae0  push    rdi
0x180017ae1  push    r12
0x180017ae3  push    r13
0x180017ae5  push    r14
0x180017ae7  push    r15
0x180017ae9  sub     rsp, 28h
0x180017aed  mov     r14, r9
0x180017af0  mov     rbx, r8
0x180017af3  mov     rsi, rdx
0x180017af6  mov     rdi, rcx
0x180017af9  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b00  lea     r12, WPP_GLOBAL_Control
0x180017b07  lea     r13, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x180017b0e  cmp     rcx, r12
0x180017b11  jz      short loc_180017B2A
0x180017b13  test    byte ptr [rcx+1Ch], 8
0x180017b17  jz      short loc_180017B2A
0x180017b19  mov     rcx, [rcx+10h]
0x180017b1d  mov     edx, 0A9h
0x180017b22  mov     r8, r13
0x180017b25  call    WPP_SF_
0x180017b2a  lea     rbp, [rdi+110h]
0x180017b31  mov     rcx, rbp; lpCriticalSection
0x180017b34  call    cs:__imp_EnterCriticalSection
0x180017b3a  mov     rcx, rdi; this
0x180017b3d  call    ?ResetInactivityTimerIfNotSharing@TetheringService@@AEAAXXZ; TetheringService::ResetInactivityTimerIfNotSharing(void)
0x180017b42  xor     r15d, r15d
0x180017b45  test    rsi, rsi
0x180017b48  jnz     short loc_180017B80
0x180017b4a  test    rbx, rbx
0x180017b4d  jnz     loc_180017C20
0x180017b53  mov     r9d, 80070057h
0x180017b59  mov     esi, r9d
0x180017b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b63  cmp     rcx, r12
0x180017b66  jz      loc_180017E10
0x180017b6c  test    byte ptr [rcx+1Ch], 1
0x180017b70  jz      loc_180017E10
0x180017b76  mov     edx, 0AAh
0x180017b7b  jmp     loc_180017E04
0x180017b80  mov     ecx, 6
0x180017b85  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x180017b8a  test    rax, rax
0x180017b8d  jz      loc_180017DE4
0x180017b93  movups  xmm0, xmmword ptr [rax]
0x180017b96  mov     rcx, rax; Block
0x180017b99  movups  xmmword ptr [rsi], xmm0
0x180017b9c  movups  xmm1, xmmword ptr [rax+10h]
0x180017ba0  movups  xmmword ptr [rsi+10h], xmm1
0x180017ba4  movups  xmm0, xmmword ptr [rax+20h]
0x180017ba8  movups  xmmword ptr [rsi+20h], xmm0
0x180017bac  movups  xmm1, xmmword ptr [rax+30h]
0x180017bb0  movups  xmmword ptr [rsi+30h], xmm1
0x180017bb4  movups  xmm0, xmmword ptr [rax+40h]
0x180017bb8  movups  xmmword ptr [rsi+40h], xmm0
0x180017bbc  movups  xmm1, xmmword ptr [rax+50h]
0x180017bc0  movups  xmmword ptr [rsi+50h], xmm1
0x180017bc4  movups  xmm0, xmmword ptr [rax+60h]
0x180017bc8  movups  xmmword ptr [rsi+60h], xmm0
0x180017bcc  movups  xmm1, xmmword ptr [rax+70h]
0x180017bd0  movups  xmmword ptr [rsi+70h], xmm1
0x180017bd4  movups  xmm0, xmmword ptr [rax+80h]
0x180017bdb  movups  xmmword ptr [rsi+80h], xmm0
0x180017be2  movups  xmm1, xmmword ptr [rax+90h]
0x180017be9  movups  xmmword ptr [rsi+90h], xmm1
0x180017bf0  movups  xmm0, xmmword ptr [rax+0A0h]
0x180017bf7  movups  xmmword ptr [rsi+0A0h], xmm0
0x180017bfe  movups  xmm1, xmmword ptr [rax+0B0h]
0x180017c05  movups  xmmword ptr [rsi+0B0h], xmm1
0x180017c0c  movups  xmm0, xmmword ptr [rax+0C0h]
0x180017c13  movups  xmmword ptr [rsi+0C0h], xmm0
0x180017c1a  call    cs:__imp_free
0x180017c20  mov     esi, r15d
0x180017c23  test    rbx, rbx
0x180017c26  jz      loc_180017E10
0x180017c2c  test    r14, r14
0x180017c2f  jnz     short loc_180017C5E
0x180017c31  mov     r9d, 80070057h
0x180017c37  mov     esi, r9d
0x180017c3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c41  cmp     rcx, r12
0x180017c44  jz      loc_180017E10
0x180017c4a  test    byte ptr [rcx+1Ch], 1
0x180017c4e  jz      loc_180017E10
0x180017c54  mov     edx, 0ACh
0x180017c59  jmp     loc_180017E04
0x180017c5e  movzx   eax, byte ptr [rdi+0DCh]
0x180017c65  mov     [r14], eax
0x180017c68  cmp     [rdi+0DCh], r15b
0x180017c6f  jz      loc_180017D20
0x180017c75  mov     eax, [rdi+8]
0x180017c78  lea     r9, [rdi+0Ch]
0x180017c7c  mov     r8d, 7FFFFFFEh
0x180017c82  mov     [rbx], eax
0x180017c84  mov     ecx, r8d
0x180017c87  lea     rax, [rbx+4]
0x180017c8b  mov     edx, 21h ; '!'
0x180017c90  test    rcx, rcx
0x180017c93  jz      short loc_180017CB4
0x180017c95  movzx   r10d, word ptr [r9]
0x180017c99  test    r10w, r10w
0x180017c9d  jz      short loc_180017CB4
0x180017c9f  mov     [rax], r10w
0x180017ca3  add     r9, 2
0x180017ca7  add     rax, 2
0x180017cab  dec     rcx
0x180017cae  sub     rdx, 1
0x180017cb2  jnz     short loc_180017C90
0x180017cb4  test    rdx, rdx
0x180017cb7  lea     rcx, [rax-2]
0x180017cbb  mov     edx, 41h ; 'A'
0x180017cc0  cmovnz  rcx, rax
0x180017cc4  lea     rax, [rbx+46h]
0x180017cc8  mov     [rcx], r15w
0x180017ccc  lea     rcx, [rdi+4Eh]
0x180017cd0  test    r8, r8
0x180017cd3  jz      short loc_180017CF4
0x180017cd5  movzx   r9d, word ptr [rcx]
0x180017cd9  test    r9w, r9w
0x180017cdd  jz      short loc_180017CF4
0x180017cdf  mov     [rax], r9w
0x180017ce3  add     rcx, 2
0x180017ce7  add     rax, 2
0x180017ceb  dec     r8
0x180017cee  sub     rdx, 1
0x180017cf2  jnz     short loc_180017CD0
0x180017cf4  lea     rcx, [rax-2]
0x180017cf8  test    rdx, rdx
0x180017cfb  cmovnz  rcx, rax
0x180017cff  mov     [rcx], r15w
0x180017d03  mov     eax, [rdi+0D0h]
0x180017d09  mov     [rbx+0C8h], eax
0x180017d0f  mov     eax, [rdi+0D4h]
0x180017d15  mov     [rbx+0CCh], eax
0x180017d1b  jmp     loc_180017E10
0x180017d20  mov     ecx, 7
0x180017d25  call    ?TetheringSettingsGetSettingValueGlobalInternal@@YAPEAXW4TetheringSettingGlobal@@@Z; TetheringSettingsGetSettingValueGlobalInternal(TetheringSettingGlobal)
0x180017d2a  test    rax, rax
0x180017d2d  jz      loc_180017DC2
0x180017d33  movups  xmm0, xmmword ptr [rax]
0x180017d36  mov     rcx, rax; Block
0x180017d39  movups  xmmword ptr [rbx], xmm0
0x180017d3c  movups  xmm1, xmmword ptr [rax+10h]
0x180017d40  movups  xmmword ptr [rbx+10h], xmm1
0x180017d44  movups  xmm0, xmmword ptr [rax+20h]
0x180017d48  movups  xmmword ptr [rbx+20h], xmm0
0x180017d4c  movups  xmm1, xmmword ptr [rax+30h]
0x180017d50  movups  xmmword ptr [rbx+30h], xmm1
0x180017d54  movups  xmm0, xmmword ptr [rax+40h]
0x180017d58  movups  xmmword ptr [rbx+40h], xmm0
0x180017d5c  movups  xmm1, xmmword ptr [rax+50h]
0x180017d60  movups  xmmword ptr [rbx+50h], xmm1
0x180017d64  movups  xmm0, xmmword ptr [rax+60h]
0x180017d68  movups  xmmword ptr [rbx+60h], xmm0
0x180017d6c  movups  xmm1, xmmword ptr [rax+70h]
0x180017d70  movups  xmmword ptr [rbx+70h], xmm1
0x180017d74  movups  xmm0, xmmword ptr [rax+80h]
0x180017d7b  movups  xmmword ptr [rbx+80h], xmm0
0x180017d82  movups  xmm1, xmmword ptr [rax+90h]
0x180017d89  movups  xmmword ptr [rbx+90h], xmm1
0x180017d90  movups  xmm0, xmmword ptr [rax+0A0h]
0x180017d97  movups  xmmword ptr [rbx+0A0h], xmm0
0x180017d9e  movups  xmm1, xmmword ptr [rax+0B0h]
0x180017da5  movups  xmmword ptr [rbx+0B0h], xmm1
0x180017dac  movups  xmm0, xmmword ptr [rax+0C0h]
0x180017db3  movups  xmmword ptr [rbx+0C0h], xmm0
0x180017dba  call    cs:__imp_free
0x180017dc0  jmp     short loc_180017E10
0x180017dc2  mov     r9d, 83120006h
0x180017dc8  mov     esi, r9d
0x180017dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180017dd2  cmp     rcx, r12
0x180017dd5  jz      short loc_180017E10
0x180017dd7  test    byte ptr [rcx+1Ch], 1
0x180017ddb  jz      short loc_180017E10
0x180017ddd  mov     edx, 0ADh
0x180017de2  jmp     short loc_180017E04
0x180017de4  mov     r9d, 83120006h
0x180017dea  mov     esi, r9d
0x180017ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180017df4  cmp     rcx, r12
0x180017df7  jz      short loc_180017E10
0x180017df9  test    byte ptr [rcx+1Ch], 1
0x180017dfd  jz      short loc_180017E10
0x180017dff  mov     edx, 0ABh
0x180017e04  mov     rcx, [rcx+10h]
0x180017e08  mov     r8, r13
0x180017e0b  call    WPP_SF_d
0x180017e10  mov     rcx, rbp; lpCriticalSection
0x180017e13  call    cs:__imp_LeaveCriticalSection
0x180017e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e20  cmp     rcx, r12
0x180017e23  jz      short loc_180017E3F
0x180017e25  test    byte ptr [rcx+1Ch], 8
0x180017e29  jz      short loc_180017E3F
0x180017e2b  mov     rcx, [rcx+10h]
0x180017e2f  mov     edx, 0AEh
0x180017e34  mov     r9d, esi
0x180017e37  mov     r8, r13
0x180017e3a  call    WPP_SF_d
0x180017e3f  mov     eax, esi
0x180017e41  add     rsp, 28h
0x180017e45  pop     r15
0x180017e47  pop     r14
0x180017e49  pop     r13
0x180017e4b  pop     r12
0x180017e4d  pop     rdi
0x180017e4e  pop     rsi
0x180017e4f  pop     rbp
0x180017e50  pop     rbx
0x180017e51  retn
```
