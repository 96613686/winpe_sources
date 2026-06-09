# SensFireWinlogonEventHelper(ushort const *,ulong,SENS_EVENT_TYPE)

- ea: `0x180003e00`
- end: `0x1800041f5`
- name: `?SensFireWinlogonEventHelper@@YAJPEBGKW4SENS_EVENT_TYPE@@@Z`
- size: `1013`
- prototype: `__int64 __fastcall(const OLECHAR *, unsigned int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003bd0`

## callees

- `0x180003e00`
- `0x180008260`
- `0x180008300`
- `0x1800093b0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003e49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003eef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003e49`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003eef`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f5a`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f5a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041dd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800041dd`

## pseudocode

```c
__int64 __fastcall SensFireWinlogonEventHelper(const OLECHAR *a1, unsigned int a2, int a3)
{
  OLECHAR *v3; // r14
  HRESULT v5; // eax
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // r13d
  BSTR v10; // rax
  __int64 v11; // r8
  LPVOID v12; // rcx
  __int64 (__fastcall *v13)(LPVOID, OLECHAR *, _QWORD); // rax
  unsigned int v14; // r15d
  _QWORD *v15; // rcx
  int v16; // eax
  int v17; // eax
  LPVOID v18; // rcx
  __int64 (__fastcall *v19)(LPVOID, OLECHAR *, _QWORD); // rax
  int v20; // eax
  __int64 v21; // rdx
  LPVOID v23; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  ppv = 0;
  v23 = 0;
  v5 = CoCreateInstance(&SENSGUID_EVENTCLASS_LOGON, 0, 0x15u, &IID_ISensLogon, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 40;
LABEL_6:
      WPP_SF_d(v7[2], v8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, (unsigned int)v5);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
  }
  v5 = CoCreateInstance(&SENSGUID_EVENTCLASS_LOGON2, 0, 0x15u, &IID_ISensLogon2, &v23);
  v9 = v5;
  if ( v5 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids);
    }
    v10 = SysAllocString(a1);
    v3 = v10;
    if ( !v10 )
    {
      v6 = -2147024882;
      goto LABEL_71;
    }
    if ( a3 <= 8 )
    {
      switch ( a3 )
      {
        case 8:
          v12 = v23;
          v13 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v23 + 80LL);
          goto LABEL_31;
        case 2:
          v20 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 56LL))(ppv, v10);
          v18 = v23;
          v6 = v20;
          v19 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v23 + 56LL);
          break;
        case 3:
          v17 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 64LL))(ppv, v10);
          v18 = v23;
          v6 = v17;
          v19 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v23 + 64LL);
          break;
        case 5:
          v16 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 72LL))(ppv, v10);
          goto LABEL_61;
        case 6:
          v12 = v23;
          v13 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v23 + 88LL);
          goto LABEL_31;
        case 7:
          v12 = v23;
          v13 = *(__int64 (__fastcall **)(LPVOID, OLECHAR *, _QWORD))(*(_QWORD *)v23 + 72LL);
LABEL_31:
          v14 = a2;
          v9 = v13(v12, v3, a2);
LABEL_32:
          v15 = WPP_GLOBAL_Control;
          goto LABEL_47;
        default:
LABEL_42:
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              44,
              WPP_7617987f8fa93304f2df28234d8870cd_Traceguids,
              (unsigned int)a3);
            v15 = WPP_GLOBAL_Control;
          }
          v14 = a2;
LABEL_47:
          if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
          {
            v21 = 46;
LABEL_51:
            WPP_SF_d(v15[2], v21, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids, (unsigned int)v6);
            v15 = WPP_GLOBAL_Control;
            goto LABEL_52;
          }
          goto LABEL_52;
      }
      v14 = a2;
      v9 = v19(v18, v3, a2);
      goto LABEL_62;
    }
    switch ( a3 )
    {
      case 10:
        v16 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 80LL))(ppv, v10);
        break;
      case 11:
        v16 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 88LL))(ppv, v10);
        break;
      case 12:
        v16 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 96LL))(ppv, v10);
        break;
      case 13:
        v16 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 104LL))(ppv, v10);
        break;
      default:
        goto LABEL_42;
    }
LABEL_61:
    v14 = a2;
    v6 = v16;
LABEL_62:
    if ( v6 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 45;
        goto LABEL_51;
      }
LABEL_52:
      if ( v9 >= 0 )
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
          WPP_SF_dD(v15[2], 48, v11, v14, v6);
      }
      else if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 2u )
      {
        WPP_SF_dD(v15[2], 47, v11, v14, v9);
      }
      goto LABEL_71;
    }
    goto LABEL_32;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 42;
    goto LABEL_6;
  }
LABEL_71:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v23 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
  SysFreeString(v3);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003e00  mov     [rsp-38h+arg_8], edx
0x180003e04  mov     [rsp-38h+psz], rcx
0x180003e09  push    rbp
0x180003e0a  push    rbx
0x180003e0b  push    rsi
0x180003e0c  push    r12
0x180003e0e  push    r13
0x180003e10  push    r14
0x180003e12  push    r15
0x180003e14  mov     rbp, rsp
0x180003e17  sub     rsp, 40h
0x180003e1b  xor     r14d, r14d
0x180003e1e  lea     rax, [rbp+arg_18]
0x180003e22  mov     r15d, r8d
0x180003e25  mov     [rbp+arg_18], r14
0x180003e29  lea     r9, IID_ISensLogon; riid
0x180003e30  mov     [rbp+var_10], r14
0x180003e34  xor     edx, edx; pUnkOuter
0x180003e36  mov     [rsp+40h+ppv], rax; ppv
0x180003e3b  lea     r13d, [r14+15h]
0x180003e3f  mov     r8d, r13d; dwClsContext
0x180003e42  lea     rcx, SENSGUID_EVENTCLASS_LOGON; rclsid
0x180003e49  call    cs:__imp_CoCreateInstance
0x180003e4f  mov     ebx, eax
0x180003e51  test    eax, eax
0x180003e53  jns     short loc_180003E9C
0x180003e55  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e5c  lea     rsi, WPP_GLOBAL_Control
0x180003e63  cmp     rcx, rsi
0x180003e66  jz      loc_1800041B0
0x180003e6c  test    byte ptr [rcx+1Ch], 1
0x180003e70  jz      loc_1800041B0
0x180003e76  cmp     byte ptr [rcx+19h], 2
0x180003e7a  jb      loc_1800041B0
0x180003e80  lea     edx, [r14+28h]
0x180003e84  lea     r8, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180003e8b  mov     rcx, [rcx+10h]
0x180003e8f  mov     r9d, eax
0x180003e92  call    WPP_SF_d
0x180003e97  jmp     loc_1800041B0
0x180003e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ea3  lea     rsi, WPP_GLOBAL_Control
0x180003eaa  lea     r12, WPP_7617987f8fa93304f2df28234d8870cd_Traceguids
0x180003eb1  cmp     rcx, rsi
0x180003eb4  jz      short loc_180003ED3
0x180003eb6  test    byte ptr [rcx+1Ch], 1
0x180003eba  jz      short loc_180003ED3
0x180003ebc  cmp     byte ptr [rcx+19h], 5
0x180003ec0  jb      short loc_180003ED3
0x180003ec2  mov     rcx, [rcx+10h]
0x180003ec6  mov     edx, 29h ; ')'
0x180003ecb  mov     r8, r12
0x180003ece  call    WPP_SF_
0x180003ed3  lea     rax, [rbp+var_10]
0x180003ed7  mov     r8d, r13d; dwClsContext
0x180003eda  lea     r9, IID_ISensLogon2; riid
0x180003ee1  mov     [rsp+40h+ppv], rax; ppv
0x180003ee6  xor     edx, edx; pUnkOuter
0x180003ee8  lea     rcx, SENSGUID_EVENTCLASS_LOGON2; rclsid
0x180003eef  call    cs:__imp_CoCreateInstance
0x180003ef5  mov     r13d, eax
0x180003ef8  test    eax, eax
0x180003efa  jns     short loc_180003F2D
0x180003efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f03  cmp     rcx, rsi
0x180003f06  jz      loc_1800041B0
0x180003f0c  test    byte ptr [rcx+1Ch], 1
0x180003f10  jz      loc_1800041B0
0x180003f16  cmp     byte ptr [rcx+19h], 2
0x180003f1a  jb      loc_1800041B0
0x180003f20  mov     edx, 2Ah ; '*'
0x180003f25  mov     r8, r12
0x180003f28  jmp     loc_180003E8B
0x180003f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f34  cmp     rcx, rsi
0x180003f37  jz      short loc_180003F56
0x180003f39  test    byte ptr [rcx+1Ch], 1
0x180003f3d  jz      short loc_180003F56
0x180003f3f  cmp     byte ptr [rcx+19h], 5
0x180003f43  jb      short loc_180003F56
0x180003f45  mov     rcx, [rcx+10h]
0x180003f49  mov     edx, 2Bh ; '+'
0x180003f4e  mov     r8, r12
0x180003f51  call    WPP_SF_
0x180003f56  mov     rcx, [rbp+psz]; psz
0x180003f5a  call    cs:__imp_SysAllocString
0x180003f60  mov     r14, rax
0x180003f63  test    rax, rax
0x180003f66  jnz     short loc_180003F72
0x180003f68  mov     ebx, 8007000Eh
0x180003f6d  jmp     loc_1800041B0
0x180003f72  cmp     r15d, 8
0x180003f76  jg      loc_180004055
0x180003f7c  jz      loc_180004045
0x180003f82  mov     ecx, r15d
0x180003f85  sub     ecx, 2
0x180003f88  jz      loc_18000400E
0x180003f8e  sub     ecx, 1
0x180003f91  jz      short loc_180003FEC
0x180003f93  sub     ecx, 2
0x180003f96  jz      short loc_180003FDC
0x180003f98  sub     ecx, 1
0x180003f9b  jz      short loc_180003FB3
0x180003f9d  cmp     ecx, 1
0x180003fa0  jnz     loc_18000407C
0x180003fa6  mov     rcx, [rbp+var_10]
0x180003faa  mov     rax, [rcx]
0x180003fad  mov     rax, [rax+48h]
0x180003fb1  jmp     short loc_180003FBE
0x180003fb3  mov     rcx, [rbp+var_10]
0x180003fb7  mov     rax, [rcx]
0x180003fba  mov     rax, [rax+58h]
0x180003fbe  mov     r15d, [rbp+arg_8]
0x180003fc2  mov     rdx, r14
0x180003fc5  mov     r8d, r15d
0x180003fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fcd  mov     r13d, eax
0x180003fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd7  jmp     loc_1800040B3
0x180003fdc  mov     rcx, [rbp+arg_18]
0x180003fe0  mov     rax, [rcx]
0x180003fe3  mov     rax, [rax+48h]
0x180003fe7  jmp     loc_180004146
0x180003fec  mov     rcx, [rbp+arg_18]
0x180003ff0  mov     rdx, r14
0x180003ff3  mov     rax, [rcx]
0x180003ff6  mov     rax, [rax+40h]
0x180003ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fff  mov     rcx, [rbp+var_10]
0x180004003  mov     ebx, eax
0x180004005  mov     rax, [rcx]
0x180004008  mov     rax, [rax+40h]
0x18000400c  jmp     short loc_18000402E
0x18000400e  mov     rcx, [rbp+arg_18]
0x180004012  mov     rdx, r14
0x180004015  mov     rax, [rcx]
0x180004018  mov     rax, [rax+38h]
0x18000401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004021  mov     rcx, [rbp+var_10]
0x180004025  mov     ebx, eax
0x180004027  mov     rax, [rcx]
0x18000402a  mov     rax, [rax+38h]
0x18000402e  mov     r15d, [rbp+arg_8]
0x180004032  mov     rdx, r14
0x180004035  mov     r8d, r15d
0x180004038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403d  mov     r13d, eax
0x180004040  jmp     loc_180004154
0x180004045  mov     rcx, [rbp+var_10]
0x180004049  mov     rax, [rcx]
0x18000404c  mov     rax, [rax+50h]
0x180004050  jmp     loc_180003FBE
0x180004055  mov     ecx, r15d
0x180004058  sub     ecx, 0Ah
0x18000405b  jz      loc_18000413B
0x180004061  sub     ecx, 1
0x180004064  jz      loc_18000412E
0x18000406a  sub     ecx, 1
0x18000406d  jz      loc_180004121
0x180004073  cmp     ecx, 1
0x180004076  jz      loc_180004114
0x18000407c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004083  cmp     rcx, rsi
0x180004086  jz      short loc_1800040AF
0x180004088  test    byte ptr [rcx+1Ch], 1
0x18000408c  jz      short loc_1800040AF
0x18000408e  cmp     byte ptr [rcx+19h], 3
0x180004092  jb      short loc_1800040AF
0x180004094  mov     rcx, [rcx+10h]
0x180004098  mov     edx, 2Ch ; ','
0x18000409d  mov     r9d, r15d
0x1800040a0  mov     r8, r12
0x1800040a3  call    WPP_SF_d
0x1800040a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040af  mov     r15d, [rbp+arg_8]
0x1800040b3  cmp     rcx, rsi
0x1800040b6  jz      short loc_1800040DF
0x1800040b8  test    byte ptr [rcx+1Ch], 1
0x1800040bc  jz      short loc_1800040DF
0x1800040be  cmp     byte ptr [rcx+19h], 5
0x1800040c2  jb      short loc_1800040DF
0x1800040c4  mov     edx, 2Eh ; '.'
0x1800040c9  mov     rcx, [rcx+10h]
0x1800040cd  mov     r9d, ebx
0x1800040d0  mov     r8, r12
0x1800040d3  call    WPP_SF_d
0x1800040d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040df  test    r13d, r13d
0x1800040e2  jns     loc_18000418A
0x1800040e8  cmp     rcx, rsi
0x1800040eb  jz      loc_1800041B0
0x1800040f1  test    byte ptr [rcx+1Ch], 1
0x1800040f5  jz      loc_1800041B0
0x1800040fb  cmp     byte ptr [rcx+19h], 2
0x1800040ff  jb      loc_1800041B0
0x180004105  mov     edx, 2Fh ; '/'
0x18000410a  mov     dword ptr [rsp+40h+ppv], r13d
0x18000410f  jmp     loc_1800041A4
0x180004114  mov     rcx, [rbp+arg_18]
0x180004118  mov     rax, [rcx]
0x18000411b  mov     rax, [rax+68h]
0x18000411f  jmp     short loc_180004146
0x180004121  mov     rcx, [rbp+arg_18]
0x180004125  mov     rax, [rcx]
0x180004128  mov     rax, [rax+60h]
0x18000412c  jmp     short loc_180004146
0x18000412e  mov     rcx, [rbp+arg_18]
0x180004132  mov     rax, [rcx]
0x180004135  mov     rax, [rax+58h]
0x180004139  jmp     short loc_180004146
0x18000413b  mov     rcx, [rbp+arg_18]
0x18000413f  mov     rax, [rcx]
0x180004142  mov     rax, [rax+50h]
0x180004146  mov     rdx, r14
0x180004149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414e  mov     r15d, [rbp+arg_8]
0x180004152  mov     ebx, eax
0x180004154  test    ebx, ebx
0x180004156  jns     loc_180003FD0
0x18000415c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004163  cmp     rcx, rsi
0x180004166  jz      loc_1800040DF
0x18000416c  test    byte ptr [rcx+1Ch], 1
0x180004170  jz      loc_1800040DF
0x180004176  cmp     byte ptr [rcx+19h], 2
0x18000417a  jb      loc_1800040DF
0x180004180  mov     edx, 2Dh ; '-'
0x180004185  jmp     loc_1800040C9
0x18000418a  cmp     rcx, rsi
0x18000418d  jz      short loc_1800041B0
0x18000418f  test    byte ptr [rcx+1Ch], 1
0x180004193  jz      short loc_1800041B0
0x180004195  cmp     byte ptr [rcx+19h], 5
0x180004199  jb      short loc_1800041B0
0x18000419b  mov     edx, 30h ; '0'
0x1800041a0  mov     dword ptr [rsp+40h+ppv], ebx
0x1800041a4  mov     rcx, [rcx+10h]
0x1800041a8  mov     r9d, r15d
0x1800041ab  call    WPP_SF_dD
0x1800041b0  mov     rcx, [rbp+arg_18]
0x1800041b4  test    rcx, rcx
0x1800041b7  jz      short loc_1800041C5
0x1800041b9  mov     rax, [rcx]
0x1800041bc  mov     rax, [rax+10h]
0x1800041c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c5  mov     rcx, [rbp+var_10]
0x1800041c9  test    rcx, rcx
0x1800041cc  jz      short loc_1800041DA
0x1800041ce  mov     rax, [rcx]
0x1800041d1  mov     rax, [rax+10h]
0x1800041d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041da  mov     rcx, r14; bstrString
0x1800041dd  call    cs:__imp_SysFreeString
0x1800041e3  mov     eax, ebx
0x1800041e5  add     rsp, 40h
0x1800041e9  pop     r15
0x1800041eb  pop     r14
0x1800041ed  pop     r13
0x1800041ef  pop     r12
0x1800041f1  pop     rsi
0x1800041f2  pop     rbx
0x1800041f3  pop     rbp
0x1800041f4  retn
```
