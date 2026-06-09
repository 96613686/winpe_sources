# UbpmProxySingleton::StopInstances(JobMoniker const &,User const *,_GUID const *)

- ea: `0x1800785f4`
- end: `0x1800788db`
- name: `?StopInstances@UbpmProxySingleton@@AEAAJAEBVJobMoniker@@PEBVUser@@PEBU_GUID@@@Z`
- size: `743`
- prototype: `int(UbpmProxySingleton *__hidden this, const struct JobMoniker *, const struct User *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800785e0`
- `0x1800788f0`

## callees

- `0x18000b4e0`
- `0x18002af2c`
- `0x18002e4e4`
- `0x180040590`
- `0x180042fa4`
- `0x180043a0c`
- `0x18004b284`
- `0x180051b3c`
- `0x180056794`
- `0x1800785f4`
- `0x18007e68a`

## import_xrefs

- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x18007871d`
- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x18007871d`
- `UBPM!UbpmCloseTriggerConsumer` at `0x1800788b6`
- `UBPM!UbpmCloseTriggerConsumer` at `0x1800788b6`
- `UBPM!UbpmTriggerConsumerControl` at `0x1800786fe`
- `UBPM!UbpmTriggerConsumerControl` at `0x1800787ff`
- `UBPM!UbpmTriggerConsumerControl` at `0x1800786fe`
- `UBPM!UbpmTriggerConsumerControl` at `0x1800787ff`
- `RPCRT4!RpcRevertToSelf` at `0x1800786ae`
- `RPCRT4!RpcRevertToSelf` at `0x1800786c9`
- `RPCRT4!RpcRevertToSelf` at `0x1800786ae`
- `RPCRT4!RpcRevertToSelf` at `0x1800786c9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800786ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800786ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UbpmProxySingleton::StopInstances(
        UbpmProxySingleton *this,
        const struct JobMoniker *a2,
        const struct User *a3,
        const struct _GUID *a4)
{
  const struct JobMoniker *v6; // rsi
  UbpmProxySingleton *v7; // rcx
  int ClientUser; // ebx
  const struct _GUID *v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // r12d
  unsigned int i; // esi
  __int64 v15; // r15
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 *v20; // [rsp+38h] [rbp-39h] BYREF
  __int64 v21; // [rsp+40h] [rbp-31h] BYREF
  __int64 v22; // [rsp+48h] [rbp-29h] BYREF
  PSID pSid; // [rsp+50h] [rbp-21h] BYREF
  _DWORD v24[4]; // [rsp+58h] [rbp-19h] BYREF
  DWORD LengthSid; // [rsp+68h] [rbp-9h]
  PSID v26; // [rsp+70h] [rbp-1h]
  const struct _GUID *v27; // [rsp+78h] [rbp+7h]
  UbpmProxySingleton *v28; // [rsp+D8h] [rbp+67h] BYREF
  const struct JobMoniker *v29; // [rsp+E0h] [rbp+6Fh]

  v29 = a2;
  v28 = this;
  v6 = a2;
  v22 = 0;
  memset_0(v24, 0, 0x48u);
  v21 = 0;
  ClientUser = UbpmProxySingleton::OpenConsumer(v7, v6, (struct AutoUbpmConsumerHandle *)&v22);
  if ( ClientUser >= 0 )
  {
    v24[0] = 2;
    if ( a3 )
    {
      v11 = UbpmTriggerConsumerQueryStatus(v22, &v21);
      ClientUser = v11;
      if ( v11 > 0 )
        ClientUser = (unsigned __int16)v11 | 0x80070000;
      if ( ClientUser >= 0 )
      {
        v12 = v21;
        if ( v21 )
        {
          v13 = 0;
          v20 = &v21;
          for ( i = 0; i < *(_DWORD *)(v12 + 28); ++i )
          {
            v28 = 0;
            v15 = 56LL * i;
            ClientUser = User::FromSid(
                           (struct User *)&v28,
                           *(void **)(*(_QWORD *)(v12 + 32) + v15 + 48),
                           SidTypeUnknown);
            if ( ClientUser < 0 )
              goto LABEL_34;
            if ( (unsigned __int8)User::operator==(a3, &v28) )
            {
              if ( !a4 )
                goto LABEL_27;
              v16 = *(_QWORD *)(v21 + 32);
              v17 = *(_QWORD *)&a4->Data1 - *(_QWORD *)(v16 + v15 + 16);
              if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)(v16 + v15 + 16) )
                v17 = *(_QWORD *)a4->Data4 - *(_QWORD *)(v16 + v15 + 24);
              if ( !v17 )
              {
LABEL_27:
                v27 = (const struct _GUID *)(v15 + *(_QWORD *)(v21 + 32) + 16LL);
                v26 = *(PSID *)(v15 + *(_QWORD *)(v21 + 32) + 48);
                LengthSid = *(_DWORD *)(v15 + *(_QWORD *)(v21 + 32) + 40);
                v18 = UbpmTriggerConsumerControl(v22, v24, 0);
                ClientUser = v18;
                if ( v18 == 1168 )
                {
                  ClientUser = 0;
                }
                else
                {
                  if ( v18 > 0 )
                    ClientUser = (unsigned __int16)v18 | 0x80070000;
                  if ( ClientUser < 0 )
                  {
LABEL_34:
                    wmi::AutoRef<User::UserEntry>::Release(&v28);
                    goto LABEL_37;
                  }
                  v13 = 1;
                }
              }
            }
            wmi::AutoRef<User::UserEntry>::Release(&v28);
            v12 = v21;
          }
          if ( !v13 )
            ClientUser = -2147023728;
LABEL_37:
          UbpmFreeMe::~UbpmFreeMe((UbpmFreeMe *)&v20);
          v6 = v29;
        }
        else
        {
          ClientUser = -2147418113;
        }
      }
    }
    else
    {
      v20 = 0;
      pSid = 0;
      v9 = v27;
      if ( a4 )
        v9 = a4;
      v27 = v9;
      RpcAutoImpersonate::RpcAutoImpersonate((RpcAutoImpersonate *)&v28, L"UbpmProxySingleton::StopInstances", 1);
      ClientUser = RpcAutoImpersonate::GetClientUser((RpcAutoImpersonate *)&v28, (struct User *)&v20);
      if ( ClientUser >= 0 )
      {
        if ( (_DWORD)v28 )
          RpcRevertToSelf();
        ClientUser = User::LookupSid((User *)&v20, &pSid);
        if ( ClientUser >= 0 )
        {
          v26 = pSid;
          LengthSid = GetLengthSid(pSid);
          v10 = UbpmTriggerConsumerControl(v22, v24, 0);
          ClientUser = v10;
          if ( v10 > 0 )
            ClientUser = (unsigned __int16)v10 | 0x80070000;
        }
      }
      else if ( (_DWORD)v28 )
      {
        RpcRevertToSelf();
      }
      wmi::AutoRef<User::UserEntry>::Release(&v20);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((ClientUser >> 31) & 0xFFFFFFFE) + 4 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
      *((_QWORD *)v6 + 3),
      ClientUser);
  }
  if ( v22 )
    UbpmCloseTriggerConsumer();
  return (unsigned int)ClientUser;
}

```

## disassembly

```asm
0x1800785f4  mov     rax, rsp
0x1800785f7  mov     [rax+18h], rbx
0x1800785fb  mov     [rax+20h], rsi
0x1800785ff  mov     [rax+10h], rdx
0x180078603  mov     [rax+8], rcx
0x180078607  push    rbp
0x180078608  push    r12
0x18007860a  push    r13
0x18007860c  push    r14
0x18007860e  push    r15
0x180078610  lea     rbp, [rax-5Fh]
0x180078614  sub     rsp, 0A0h
0x18007861b  mov     r14, r9
0x18007861e  mov     r13, r8
0x180078621  mov     rsi, rdx
0x180078624  mov     [rbp+57h+var_80], 0
0x18007862c  xor     edx, edx; Val
0x18007862e  lea     r8d, [rdx+48h]; Size
0x180078632  lea     rcx, [rbp+57h+var_70]; void *
0x180078636  call    memset_0
0x18007863b  mov     [rbp+57h+var_88], 0
0x180078643  lea     r8, [rbp+57h+var_80]; struct AutoUbpmConsumerHandle *
0x180078647  mov     rdx, rsi; struct JobMoniker *
0x18007864a  call    ?OpenConsumer@UbpmProxySingleton@@AEAAJAEBVJobMoniker@@AEAVAutoUbpmConsumerHandle@@@Z; UbpmProxySingleton::OpenConsumer(JobMoniker const &,AutoUbpmConsumerHandle &)
0x18007864f  mov     ebx, eax
0x180078651  test    eax, eax
0x180078653  js      loc_180078860
0x180078659  mov     [rbp+57h+var_70], 2
0x180078660  test    r13, r13
0x180078663  jnz     loc_180078715
0x180078669  mov     [rbp+57h+var_90], r13
0x18007866d  mov     [rbp+57h+pSid], r13
0x180078671  mov     rax, [rbp+57h+var_50]
0x180078675  test    r14, r14
0x180078678  cmovnz  rax, r14
0x18007867c  mov     [rbp+57h+var_50], rax
0x180078680  lea     r8d, [r13+1]; int
0x180078684  lea     rdx, aUbpmproxysingl; "UbpmProxySingleton::StopInstances"
0x18007868b  lea     rcx, [rbp+57h+arg_0]; this
0x18007868f  call    ??0RpcAutoImpersonate@@QEAA@PEBGH@Z; RpcAutoImpersonate::RpcAutoImpersonate(ushort const *,int)
0x180078694  nop
0x180078695  lea     rdx, [rbp+57h+var_90]; struct User *
0x180078699  lea     rcx, [rbp+57h+arg_0]; this
0x18007869d  call    ?GetClientUser@RpcAutoImpersonate@@QEBAJAEAVUser@@@Z; RpcAutoImpersonate::GetClientUser(User &)
0x1800786a2  mov     ebx, eax
0x1800786a4  test    eax, eax
0x1800786a6  jns     short loc_1800786C3
0x1800786a8  cmp     dword ptr [rbp+57h+arg_0], r13d
0x1800786ac  jz      short loc_1800786B5
0x1800786ae  call    cs:__imp_RpcRevertToSelf
0x1800786b4  nop
0x1800786b5  lea     rcx, [rbp+57h+var_90]
0x1800786b9  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x1800786be  jmp     loc_180078860
0x1800786c3  cmp     dword ptr [rbp+57h+arg_0], 0
0x1800786c7  jz      short loc_1800786CF
0x1800786c9  call    cs:__imp_RpcRevertToSelf
0x1800786cf  lea     rdx, [rbp+57h+pSid]; void **
0x1800786d3  lea     rcx, [rbp+57h+var_90]; this
0x1800786d7  call    ?LookupSid@User@@QEBAJAEAPEAX@Z; User::LookupSid(void * &)
0x1800786dc  mov     ebx, eax
0x1800786de  test    eax, eax
0x1800786e0  js      short loc_1800786B5
0x1800786e2  mov     rcx, [rbp+57h+pSid]; pSid
0x1800786e6  mov     [rbp+57h+var_58], rcx
0x1800786ea  call    cs:__imp_GetLengthSid
0x1800786f0  mov     [rbp+57h+var_60], eax
0x1800786f3  xor     r8d, r8d
0x1800786f6  lea     rdx, [rbp+57h+var_70]
0x1800786fa  mov     rcx, [rbp+57h+var_80]
0x1800786fe  call    cs:__imp_UbpmTriggerConsumerControl
0x180078704  mov     ebx, eax
0x180078706  test    eax, eax
0x180078708  jle     short loc_1800786B5
0x18007870a  movzx   ebx, ax
0x18007870d  or      ebx, 80070000h
0x180078713  jmp     short loc_1800786B5
0x180078715  lea     rdx, [rbp+57h+var_88]
0x180078719  mov     rcx, [rbp+57h+var_80]
0x18007871d  call    cs:__imp_UbpmTriggerConsumerQueryStatus
0x180078723  mov     ebx, eax
0x180078725  test    eax, eax
0x180078727  jle     short loc_180078732
0x180078729  movzx   ebx, ax
0x18007872c  or      ebx, 80070000h
0x180078732  test    ebx, ebx
0x180078734  js      loc_180078860
0x18007873a  mov     rdx, [rbp+57h+var_88]
0x18007873e  test    rdx, rdx
0x180078741  jnz     short loc_18007874D
0x180078743  mov     ebx, 8000FFFFh
0x180078748  jmp     loc_180078860
0x18007874d  xor     r12d, r12d
0x180078750  lea     rax, [rbp+57h+var_88]
0x180078754  mov     [rbp+57h+var_90], rax
0x180078758  xor     esi, esi
0x18007875a  cmp     esi, [rdx+1Ch]
0x18007875d  jnb     loc_180078848
0x180078763  mov     [rbp+57h+arg_0], 0
0x18007876b  mov     eax, esi
0x18007876d  imul    r15, rax, 38h ; '8'
0x180078771  mov     rdx, [rdx+20h]
0x180078775  mov     r8d, 8; enum _SID_NAME_USE
0x18007877b  mov     rdx, [rdx+r15+30h]; void *
0x180078780  lea     rcx, [rbp+57h+arg_0]; this
0x180078784  call    ?FromSid@User@@SAJAEAV1@PEAXW4_SID_NAME_USE@@@Z; User::FromSid(User &,void *,_SID_NAME_USE)
0x180078789  mov     ebx, eax
0x18007878b  test    eax, eax
0x18007878d  js      loc_18007883D
0x180078793  lea     rdx, [rbp+57h+arg_0]
0x180078797  mov     rcx, r13
0x18007879a  call    ??8User@@QEBA_NAEBV0@@Z; User::operator==(User const &)
0x18007879f  test    al, al
0x1800787a1  jz      loc_180078829
0x1800787a7  mov     rdx, [rbp+57h+var_88]
0x1800787ab  test    r14, r14
0x1800787ae  jz      short loc_1800787CC
0x1800787b0  mov     rcx, [rdx+20h]
0x1800787b4  mov     rax, [r14]
0x1800787b7  sub     rax, [rcx+r15+10h]
0x1800787bc  jnz     short loc_1800787C7
0x1800787be  mov     rax, [r14+8]
0x1800787c2  sub     rax, [rcx+r15+18h]
0x1800787c7  test    rax, rax
0x1800787ca  jnz     short loc_180078829
0x1800787cc  mov     rcx, [rdx+20h]
0x1800787d0  add     rcx, 10h
0x1800787d4  add     rcx, r15
0x1800787d7  mov     [rbp+57h+var_50], rcx
0x1800787db  mov     rax, [rdx+20h]
0x1800787df  mov     rcx, [r15+rax+30h]
0x1800787e4  mov     [rbp+57h+var_58], rcx
0x1800787e8  mov     rax, [rdx+20h]
0x1800787ec  mov     ecx, [r15+rax+28h]
0x1800787f1  mov     [rbp+57h+var_60], ecx
0x1800787f4  xor     r8d, r8d
0x1800787f7  lea     rdx, [rbp+57h+var_70]
0x1800787fb  mov     rcx, [rbp+57h+var_80]
0x1800787ff  call    cs:__imp_UbpmTriggerConsumerControl
0x180078805  mov     ebx, eax
0x180078807  cmp     eax, 490h
0x18007880c  jnz     short loc_180078812
0x18007880e  xor     ebx, ebx
0x180078810  jmp     short loc_180078829
0x180078812  test    eax, eax
0x180078814  jle     short loc_18007881F
0x180078816  movzx   ebx, ax
0x180078819  or      ebx, 80070000h
0x18007881f  test    ebx, ebx
0x180078821  js      short loc_18007883D
0x180078823  mov     r12d, 1
0x180078829  lea     rcx, [rbp+57h+arg_0]
0x18007882d  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180078832  inc     esi
0x180078834  mov     rdx, [rbp+57h+var_88]
0x180078838  jmp     loc_18007875A
0x18007883d  lea     rcx, [rbp+57h+arg_0]
0x180078841  call    ?Release@?$AutoRef@UUserEntry@User@@@wmi@@QEAAXXZ; wmi::AutoRef<User::UserEntry>::Release(void)
0x180078846  jmp     short loc_180078853
0x180078848  mov     eax, 80070490h
0x18007884d  test    r12d, r12d
0x180078850  cmovz   ebx, eax
0x180078853  lea     rcx, [rbp+57h+var_90]; this
0x180078857  call    ??1UbpmFreeMe@@QEAA@XZ; UbpmFreeMe::~UbpmFreeMe(void)
0x18007885c  mov     rsi, [rbp+57h+arg_8]
0x180078860  lea     rax, WPP_GLOBAL_Control
0x180078867  mov     rcx, cs:WPP_GLOBAL_Control
0x18007886e  cmp     rcx, rax
0x180078871  jz      short loc_1800788AD
0x180078873  test    dword ptr [rcx+1Ch], 100h
0x18007887a  jz      short loc_1800788AD
0x18007887c  mov     edx, ebx
0x18007887e  sar     edx, 1Fh
0x180078881  and     edx, 0FFFFFFFEh
0x180078884  add     edx, 4
0x180078887  movzx   eax, byte ptr [rcx+19h]
0x18007888b  cmp     eax, edx
0x18007888d  jb      short loc_1800788AD
0x18007888f  mov     edx, 12h
0x180078894  mov     [rsp+0C0h+var_A0], ebx
0x180078898  mov     r9, [rsi+18h]
0x18007889c  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x1800788a3  mov     rcx, [rcx+10h]
0x1800788a7  call    WPP_SF_Sd
0x1800788ac  nop
0x1800788ad  mov     rcx, [rbp+57h+var_80]
0x1800788b1  test    rcx, rcx
0x1800788b4  jz      short loc_1800788BC
0x1800788b6  call    cs:__imp_UbpmCloseTriggerConsumer
0x1800788bc  mov     eax, ebx
0x1800788be  lea     r11, [rsp+0C0h+var_20]
0x1800788c6  mov     rbx, [r11+40h]
0x1800788ca  mov     rsi, [r11+48h]
0x1800788ce  mov     rsp, r11
0x1800788d1  pop     r15
0x1800788d3  pop     r14
0x1800788d5  pop     r13
0x1800788d7  pop     r12
0x1800788d9  pop     rbp
0x1800788da  retn
```
