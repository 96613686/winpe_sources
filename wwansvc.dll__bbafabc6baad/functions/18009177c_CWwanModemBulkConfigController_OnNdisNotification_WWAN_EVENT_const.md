# CWwanModemBulkConfigController::OnNdisNotification(WWAN_EVENT const *)

- ea: `0x18009177c`
- end: `0x180091b7e`
- name: `?OnNdisNotification@CWwanModemBulkConfigController@@QEAAXPEBUWWAN_EVENT@@@Z`
- size: `1026`
- prototype: `void __fastcall(CWwanModemBulkConfigController *__hidden this, const struct WWAN_EVENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003cfd8`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x18009177c`
- `0x180091d5c`
- `0x180091db4`

## string_xrefs

- `0x1800917cc`: `ModemConfigInfo: unexpected EventCodeModemConfigInfo (type %d setQueryType %d)`
- `0x18009180a`: `ModemConfigInfo:  payload sz %d smaller than expected %d`
- `0x1800917dc`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x18009187e`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x1800919b2`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x1800919df`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x180091a2c`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x180091a6f`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x180091af9`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x180091b31`: `CWwanModemBulkConfigController::OnNdisNotification`
- `0x1800919a4`: ` ModemConfigInfo query failed (0x%x) for 5GC modem. Ignoring modem config`
- `0x180091873`: ` ModemConfigInfo (ind %d) mode %d state %d reason %d prevID %S currID %S IsCurrentConfigDefault %d`
- `0x180091a0e`: ` Invalid preconfigured default NSSAI information from modem (cnt %d type %d). Ignoring modem config`
- `0x1800919d1`: `ModemConfigInfo: payload sz %d smaller than expected %d for 5GC modem. Ignoring modem config`
- `0x180091a64`: ` Invalid size (%d) for %d NSSAI's. Ignoring modem config`
- `0x180091a21`: ` modem config is not completed yet (%d)`
- `0x180091ae4`: ` ModemConfig completed currID %S cnt of S_NSSAIs %d`

## pseudocode

```c
void __fastcall CWwanModemBulkConfigController::OnNdisNotification(
        CWwanModemBulkConfigController *this,
        const struct WWAN_EVENT *a2)
{
  unsigned int v4; // r14d
  __int64 v5; // r9
  int v6; // edi
  CWwanModemBulkConfigController *v7; // rcx
  const char *v8; // rbx
  CWwanModemBulkConfigController *v9; // rcx
  const char *v10; // rax
  __int64 v11; // rdx
  unsigned __int64 v12; // r9
  __int64 v13; // r8
  int v14; // ebx
  CWwanModemBulkConfigController *v15; // rcx
  const char *v16; // rax
  char *v17; // rsi
  unsigned int i; // ebx
  __int64 v19; // [rsp+20h] [rbp-F8h]
  __int64 v20; // [rsp+28h] [rbp-F0h]
  char v21[80]; // [rsp+50h] [rbp-C8h] BYREF
  char v22[80]; // [rsp+A0h] [rbp-78h] BYREF

  if ( *((_DWORD *)a2 + 1) == 61 )
  {
    v4 = 2;
    if ( *(_DWORD *)a2 == 2 || *(_DWORD *)a2 == 1 && *((_DWORD *)a2 + 4) == 1 )
    {
      if ( *((_BYTE *)this + 16) )
      {
        if ( *(_DWORD *)a2 == 1 && *((_DWORD *)a2 + 8) )
        {
          WwanLog::Warning(
            "CWwanModemBulkConfigController::OnNdisNotification",
            (const struct _GUID *)(*((_QWORD *)this + 1) + 12536LL),
            L" ModemConfigInfo query failed (0x%x) for 5GC modem. Ignoring modem config");
        }
        else
        {
          v12 = *((unsigned int *)a2 + 22);
          if ( (unsigned int)v12 >= 0xE4 )
          {
            v13 = *((unsigned int *)a2 + 79);
            if ( !(_DWORD)v13 || *((_DWORD *)a2 + 78) == 24 )
            {
              if ( *((_DWORD *)a2 + 24) == 2 )
              {
                if ( v12 >= 16 * v13 + 228 )
                {
                  *((_DWORD *)this + 8) = 2;
                  *(_OWORD *)((char *)this + 76) = *(_OWORD *)((char *)a2 + 140);
                  *(_OWORD *)((char *)this + 92) = *(_OWORD *)((char *)a2 + 156);
                  *((_DWORD *)this + 27) = *((_DWORD *)a2 + 43);
                  *((_QWORD *)this + 31) = *((_QWORD *)a2 + 39);
                  memset_0(v21, 0, 0x41u);
                  v14 = *((_DWORD *)this + 63);
                  v16 = CWwanModemBulkConfigController::binToString(
                          v15,
                          (const unsigned __int8 *)this + 80,
                          *((_DWORD *)this + 19),
                          v21);
                  WwanLog::Info(
                    "CWwanModemBulkConfigController::OnNdisNotification",
                    (const struct _GUID *)(*((_QWORD *)this + 1) + 12536LL),
                    L" ModemConfig completed currID %S cnt of S_NSSAIs %d",
                    v16,
                    v14);
                  v17 = (char *)a2 + 320;
                  for ( i = 0; i < *((_DWORD *)this + 63); v17 += 16 )
                  {
                    LODWORD(v20) = *((_DWORD *)v17 + 3);
                    LODWORD(v19) = *((unsigned __int16 *)v17 + 3);
                    WwanLog::Info(
                      "CWwanModemBulkConfigController::OnNdisNotification",
                      0,
                      L"   S_NSSAI#%d: SST %d SD %d",
                      i++,
                      v19,
                      v20);
                  }
                }
                else
                {
                  WwanLog::Warning(
                    "CWwanModemBulkConfigController::OnNdisNotification",
                    (const struct _GUID *)(*((_QWORD *)this + 1) + 12536LL),
                    L" Invalid size (%d) for %d NSSAI's. Ignoring modem config",
                    v12,
                    *((_DWORD *)a2 + 79));
                }
              }
              else
              {
                WwanLog::Info(
                  "CWwanModemBulkConfigController::OnNdisNotification",
                  (const struct _GUID *)(*((_QWORD *)this + 1) + 12536LL),
                  L" modem config is not completed yet (%d)",
                  *((unsigned int *)a2 + 24));
                v4 = 1;
                *((_DWORD *)this + 8) = *((_DWORD *)a2 + 24);
              }
            }
            else
            {
              WwanLog::Warning(
                "CWwanModemBulkConfigController::OnNdisNotification",
                (const struct _GUID *)(*((_QWORD *)this + 1) + 12536LL),
                L" Invalid preconfigured default NSSAI information from modem (cnt %d type %d). Ignoring modem config",
                (unsigned int)v13,
                *((_DWORD *)a2 + 78));
            }
          }
          else
          {
            WwanLog::Error(
              "CWwanModemBulkConfigController::OnNdisNotification",
              0,
              L"ModemConfigInfo: payload sz %d smaller than expected %d for 5GC modem. Ignoring modem config");
          }
        }
        v11 = v4;
      }
      else
      {
        v5 = *((unsigned int *)a2 + 22);
        if ( (unsigned int)v5 < 0xE4 )
        {
          WwanLog::Error(
            "CWwanModemBulkConfigController::OnNdisNotification",
            0,
            L"ModemConfigInfo:  payload sz %d smaller than expected %d",
            v5,
            228);
          return;
        }
        memset_0(v22, 0, 0x41u);
        memset_0(v21, 0, 0x41u);
        v6 = *((_DWORD *)a2 + 44);
        v8 = CWwanModemBulkConfigController::binToString(
               v7,
               (const unsigned __int8 *)a2 + 144,
               *((_DWORD *)a2 + 35),
               v22);
        v10 = CWwanModemBulkConfigController::binToString(
                v9,
                (const unsigned __int8 *)a2 + 108,
                *((_DWORD *)a2 + 26),
                v21);
        WwanLog::Info(
          "CWwanModemBulkConfigController::OnNdisNotification",
          (const struct _GUID *)(*((_QWORD *)this + 1) + 12536LL),
          L" ModemConfigInfo (ind %d) mode %d state %d reason %d prevID %S currID %S IsCurrentConfigDefault %d",
          *(_DWORD *)a2 == 2,
          *((_DWORD *)a2 + 23),
          *((_DWORD *)a2 + 24),
          *((_DWORD *)a2 + 25),
          v10,
          v8,
          v6);
        if ( *(_DWORD *)a2 == 1 && *((_DWORD *)a2 + 4) == 1 )
        {
          *((_DWORD *)this + 6) = *((_DWORD *)a2 + 23);
          return;
        }
        *(_OWORD *)((char *)this + 28) = *(_OWORD *)((char *)a2 + 92);
        *(_OWORD *)((char *)this + 44) = *(_OWORD *)((char *)a2 + 108);
        *(_OWORD *)((char *)this + 60) = *(_OWORD *)((char *)a2 + 124);
        *(_OWORD *)((char *)this + 76) = *(_OWORD *)((char *)a2 + 140);
        *(_OWORD *)((char *)this + 92) = *(_OWORD *)((char *)a2 + 156);
        *(_OWORD *)((char *)this + 108) = *(_OWORD *)((char *)a2 + 172);
        *(_OWORD *)((char *)this + 124) = *(_OWORD *)((char *)a2 + 188);
        *(_OWORD *)((char *)this + 140) = *(_OWORD *)((char *)a2 + 204);
        *(_OWORD *)((char *)this + 156) = *(_OWORD *)((char *)a2 + 220);
        *(_OWORD *)((char *)this + 172) = *(_OWORD *)((char *)a2 + 236);
        *(_OWORD *)((char *)this + 188) = *(_OWORD *)((char *)a2 + 252);
        *(_OWORD *)((char *)this + 204) = *(_OWORD *)((char *)a2 + 268);
        *(_OWORD *)((char *)this + 220) = *(_OWORD *)((char *)a2 + 284);
        *(_OWORD *)((char *)this + 236) = *(_OWORD *)((char *)a2 + 300);
        *((_DWORD *)this + 63) = *((_DWORD *)a2 + 79);
        v11 = (unsigned int)(*((_DWORD *)this + 8) != 1) + 1;
      }
      CWwanModemBulkConfigController::fsmEventHandler(this, v11);
    }
    else
    {
      WwanLog::Error(
        "CWwanModemBulkConfigController::OnNdisNotification",
        0,
        L"ModemConfigInfo: unexpected EventCodeModemConfigInfo (type %d setQueryType %d)",
        *(unsigned int *)a2,
        *((_DWORD *)a2 + 4));
    }
  }
}

```

## disassembly

```asm
0x18009177c  mov     [rsp+arg_10], rbx
0x180091781  mov     [rsp+arg_18], rbp
0x180091786  push    rsi
0x180091787  push    rdi
0x180091788  push    r14
0x18009178a  sub     rsp, 100h
0x180091791  mov     rax, cs:__security_cookie
0x180091798  xor     rax, rsp
0x18009179b  mov     [rsp+118h+var_28], rax
0x1800917a3  cmp     dword ptr [rdx+4], 3Dh ; '='
0x1800917a7  mov     rsi, rdx
0x1800917aa  mov     rbp, rcx
0x1800917ad  jnz     loc_180091B56
0x1800917b3  mov     r14d, 2
0x1800917b9  cmp     [rdx], r14d
0x1800917bc  jz      short loc_1800917ED
0x1800917be  cmp     dword ptr [rdx], 1
0x1800917c1  jnz     short loc_1800917C9
0x1800917c3  cmp     dword ptr [rdx+10h], 1
0x1800917c7  jz      short loc_1800917ED
0x1800917c9  mov     eax, [rdx+10h]
0x1800917cc  lea     r8, aModemconfiginf_0; "ModemConfigInfo: unexpected EventCodeMo"...
0x1800917d3  mov     r9d, [rdx]
0x1800917d6  mov     dword ptr [rsp+118h+var_F8], eax
0x1800917da  xor     edx, edx; struct _GUID *
0x1800917dc  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x1800917e3  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800917e8  jmp     loc_180091B56
0x1800917ed  cmp     byte ptr [rcx+10h], 0
0x1800917f1  jnz     loc_180091992
0x1800917f7  mov     r9d, [rdx+58h]
0x1800917fb  mov     eax, 0E4h
0x180091800  cmp     r9d, eax
0x180091803  jnb     short loc_180091813
0x180091805  mov     [rsp+118h+var_F8], rax
0x18009180a  lea     r8, aModemconfiginf; "ModemConfigInfo:  payload sz %d smaller"...
0x180091811  jmp     short loc_1800917DA
0x180091813  mov     ebx, 41h ; 'A'
0x180091818  lea     rcx, [rsp+118h+var_78]; void *
0x180091820  mov     r8d, ebx; Size
0x180091823  xor     edx, edx; Val
0x180091825  call    memset_0
0x18009182a  mov     r8d, ebx; Size
0x18009182d  lea     rcx, [rsp+118h+var_C8]; void *
0x180091832  xor     edx, edx; Val
0x180091834  call    memset_0
0x180091839  mov     r8d, [rsi+8Ch]; unsigned int
0x180091840  lea     rdx, [rsi+90h]; unsigned __int8 *
0x180091847  mov     edi, [rsi+0B0h]
0x18009184d  lea     r9, [rsp+118h+var_78]; char *
0x180091855  call    ?binToString@CWwanModemBulkConfigController@@AEAAPEBDPEBEKPEAD@Z; CWwanModemBulkConfigController::binToString(uchar const *,ulong,char *)
0x18009185a  mov     r8d, [rsi+68h]; unsigned int
0x18009185e  lea     rdx, [rsi+6Ch]; unsigned __int8 *
0x180091862  lea     r9, [rsp+118h+var_C8]; char *
0x180091867  mov     rbx, rax
0x18009186a  call    ?binToString@CWwanModemBulkConfigController@@AEAAPEBDPEBEKPEAD@Z; CWwanModemBulkConfigController::binToString(uchar const *,ulong,char *)
0x18009186f  mov     rdx, [rbp+8]
0x180091873  lea     r8, aModemconfiginf_2; " ModemConfigInfo (ind %d) mode %d state"...
0x18009187a  mov     [rsp+118h+var_D0], edi
0x18009187e  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x180091885  mov     [rsp+118h+var_D8], rbx
0x18009188a  xor     r9d, r9d
0x18009188d  cmp     [rsi], r14d
0x180091890  mov     [rsp+118h+var_E0], rax
0x180091895  mov     eax, [rsi+64h]
0x180091898  setz    r9b
0x18009189c  mov     [rsp+118h+var_E8], eax
0x1800918a0  add     rdx, 30F8h; struct _GUID *
0x1800918a7  mov     eax, [rsi+60h]
0x1800918aa  mov     dword ptr [rsp+118h+var_F0], eax
0x1800918ae  mov     eax, [rsi+5Ch]
0x1800918b1  mov     dword ptr [rsp+118h+var_F8], eax
0x1800918b5  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800918ba  cmp     dword ptr [rsi], 1
0x1800918bd  jnz     short loc_1800918D0
0x1800918bf  cmp     dword ptr [rsi+10h], 1
0x1800918c3  jnz     short loc_1800918D0
0x1800918c5  mov     eax, [rsi+5Ch]
0x1800918c8  mov     [rbp+18h], eax
0x1800918cb  jmp     loc_180091B56
0x1800918d0  movups  xmm0, xmmword ptr [rsi+5Ch]
0x1800918d4  xor     edx, edx
0x1800918d6  movups  xmmword ptr [rbp+1Ch], xmm0
0x1800918da  movups  xmm1, xmmword ptr [rsi+6Ch]
0x1800918de  movups  xmmword ptr [rbp+2Ch], xmm1
0x1800918e2  movups  xmm0, xmmword ptr [rsi+7Ch]
0x1800918e6  movups  xmmword ptr [rbp+3Ch], xmm0
0x1800918ea  movups  xmm1, xmmword ptr [rsi+8Ch]
0x1800918f1  movups  xmmword ptr [rbp+4Ch], xmm1
0x1800918f5  movups  xmm0, xmmword ptr [rsi+9Ch]
0x1800918fc  movups  xmmword ptr [rbp+5Ch], xmm0
0x180091900  movups  xmm1, xmmword ptr [rsi+0ACh]
0x180091907  movups  xmmword ptr [rbp+6Ch], xmm1
0x18009190b  movups  xmm0, xmmword ptr [rsi+0BCh]
0x180091912  movups  xmmword ptr [rbp+7Ch], xmm0
0x180091916  movups  xmm1, xmmword ptr [rsi+0CCh]
0x18009191d  movups  xmmword ptr [rbp+8Ch], xmm1
0x180091924  movups  xmm0, xmmword ptr [rsi+0DCh]
0x18009192b  movups  xmmword ptr [rbp+9Ch], xmm0
0x180091932  movups  xmm1, xmmword ptr [rsi+0ECh]
0x180091939  movups  xmmword ptr [rbp+0ACh], xmm1
0x180091940  movups  xmm0, xmmword ptr [rsi+0FCh]
0x180091947  movups  xmmword ptr [rbp+0BCh], xmm0
0x18009194e  movups  xmm1, xmmword ptr [rsi+10Ch]
0x180091955  movups  xmmword ptr [rbp+0CCh], xmm1
0x18009195c  movups  xmm0, xmmword ptr [rsi+11Ch]
0x180091963  movups  xmmword ptr [rbp+0DCh], xmm0
0x18009196a  movups  xmm1, xmmword ptr [rsi+12Ch]
0x180091971  movups  xmmword ptr [rbp+0ECh], xmm1
0x180091978  mov     eax, [rsi+13Ch]
0x18009197e  mov     [rbp+0FCh], eax
0x180091984  cmp     dword ptr [rbp+20h], 1
0x180091988  setnz   dl
0x18009198b  inc     edx
0x18009198d  jmp     loc_180091B4E
0x180091992  cmp     dword ptr [rdx], 1
0x180091995  jnz     short loc_1800919C3
0x180091997  mov     r9d, [rdx+20h]
0x18009199b  test    r9d, r9d
0x18009199e  jz      short loc_1800919C3
0x1800919a0  mov     rdx, [rcx+8]
0x1800919a4  lea     r8, aModemconfiginf_1; " ModemConfigInfo query failed (0x%x) fo"...
0x1800919ab  add     rdx, 30F8h; struct _GUID *
0x1800919b2  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x1800919b9  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x1800919be  jmp     loc_180091B4B
0x1800919c3  mov     r9d, [rdx+58h]
0x1800919c7  mov     eax, 0E4h
0x1800919cc  cmp     r9d, eax
0x1800919cf  jnb     short loc_1800919F0
0x1800919d1  lea     r8, aModemconfiginf_3; "ModemConfigInfo: payload sz %d smaller "...
0x1800919d8  mov     [rsp+118h+var_F8], rax
0x1800919dd  xor     edx, edx; struct _GUID *
0x1800919df  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x1800919e6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800919eb  jmp     loc_180091B4B
0x1800919f0  mov     r8d, [rdx+13Ch]
0x1800919f7  test    r8d, r8d
0x1800919fa  jz      short loc_180091A17
0x1800919fc  mov     ecx, [rdx+138h]
0x180091a02  cmp     ecx, 18h
0x180091a05  jz      short loc_180091A17
0x180091a07  mov     r9d, r8d
0x180091a0a  mov     dword ptr [rsp+118h+var_F8], ecx
0x180091a0e  lea     r8, aInvalidPreconf; " Invalid preconfigured default NSSAI in"...
0x180091a15  jmp     short loc_180091A6B
0x180091a17  cmp     [rdx+60h], r14d
0x180091a1b  jz      short loc_180091A50
0x180091a1d  mov     rdx, [rbp+8]
0x180091a21  lea     r8, aModemConfigIsN; " modem config is not completed yet (%d)"
0x180091a28  mov     r9d, [rsi+60h]
0x180091a2c  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x180091a33  add     rdx, 30F8h; struct _GUID *
0x180091a3a  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180091a3f  mov     eax, [rsi+60h]
0x180091a42  mov     r14d, 1
0x180091a48  mov     [rbp+20h], eax
0x180091a4b  jmp     loc_180091B4B
0x180091a50  mov     rcx, r8
0x180091a53  shl     rcx, 4
0x180091a57  add     rcx, rax
0x180091a5a  cmp     r9, rcx
0x180091a5d  jnb     short loc_180091A87
0x180091a5f  mov     dword ptr [rsp+118h+var_F8], r8d
0x180091a64  lea     r8, aInvalidSizeDFo; " Invalid size (%d) for %d NSSAI's. Igno"...
0x180091a6b  mov     rdx, [rbp+8]
0x180091a6f  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x180091a76  add     rdx, 30F8h; struct _GUID *
0x180091a7d  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x180091a82  jmp     loc_180091B4B
0x180091a87  mov     [rbp+20h], r14d
0x180091a8b  lea     rcx, [rsp+118h+var_C8]; void *
0x180091a90  movups  xmm0, xmmword ptr [rdx+8Ch]
0x180091a97  movups  xmmword ptr [rbp+4Ch], xmm0
0x180091a9b  movups  xmm1, xmmword ptr [rdx+9Ch]
0x180091aa2  movups  xmmword ptr [rbp+5Ch], xmm1
0x180091aa6  mov     eax, [rdx+0ACh]
0x180091aac  mov     [rbp+6Ch], eax
0x180091aaf  mov     rax, [rdx+138h]
0x180091ab6  xor     edx, edx; Val
0x180091ab8  mov     [rbp+0F8h], rax
0x180091abf  lea     r8d, [rdx+41h]; Size
0x180091ac3  call    memset_0
0x180091ac8  mov     r8d, [rbp+4Ch]; unsigned int
0x180091acc  lea     rdx, [rbp+50h]; unsigned __int8 *
0x180091ad0  mov     ebx, [rbp+0FCh]
0x180091ad6  lea     r9, [rsp+118h+var_C8]; char *
0x180091adb  call    ?binToString@CWwanModemBulkConfigController@@AEAAPEBDPEBEKPEAD@Z; CWwanModemBulkConfigController::binToString(uchar const *,ulong,char *)
0x180091ae0  mov     rdx, [rbp+8]
0x180091ae4  lea     r8, aModemconfigCom; " ModemConfig completed currID %S cnt of"...
0x180091aeb  add     rdx, 30F8h; struct _GUID *
0x180091af2  mov     dword ptr [rsp+118h+var_F8], ebx
0x180091af6  mov     r9, rax
0x180091af9  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x180091b00  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180091b05  add     rsi, 140h
0x180091b0c  xor     ebx, ebx
0x180091b0e  cmp     [rbp+0FCh], ebx
0x180091b14  jbe     short loc_180091B4B
0x180091b16  movzx   ecx, word ptr [rsi+6]
0x180091b1a  lea     r8, aSNssaiDSstDSdD; "   S_NSSAI#%d: SST %d SD %d"
0x180091b21  mov     eax, [rsi+0Ch]
0x180091b24  mov     r9d, ebx
0x180091b27  mov     dword ptr [rsp+118h+var_F0], eax
0x180091b2b  xor     edx, edx; struct _GUID *
0x180091b2d  mov     dword ptr [rsp+118h+var_F8], ecx
0x180091b31  lea     rcx, aCwwanmodembulk_5; "CWwanModemBulkConfigController::OnNdisN"...
0x180091b38  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180091b3d  inc     ebx
0x180091b3f  lea     rsi, [rsi+10h]
0x180091b43  cmp     ebx, [rbp+0FCh]
0x180091b49  jb      short loc_180091B16
0x180091b4b  mov     edx, r14d
0x180091b4e  mov     rcx, rbp
0x180091b51  call    ?fsmEventHandler@CWwanModemBulkConfigController@@AEAAXW4_WwanModemConfigStateFSMEvent@1@@Z; CWwanModemBulkConfigController::fsmEventHandler(CWwanModemBulkConfigController::_WwanModemConfigStateFSMEvent)
0x180091b56  mov     rcx, [rsp+118h+var_28]
0x180091b5e  xor     rcx, rsp; StackCookie
0x180091b61  call    __security_check_cookie
0x180091b66  lea     r11, [rsp+118h+var_18]
0x180091b6e  mov     rbx, [r11+30h]
0x180091b72  mov     rbp, [r11+38h]
0x180091b76  mov     rsp, r11
0x180091b79  pop     r14
0x180091b7b  pop     rdi
0x180091b7c  pop     rsi
0x180091b7d  retn
```
