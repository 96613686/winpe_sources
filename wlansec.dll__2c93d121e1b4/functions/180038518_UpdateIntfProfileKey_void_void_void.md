# UpdateIntfProfileKey(void *,void *,void *)

- ea: `0x180038518`
- end: `0x18003890e`
- name: `?UpdateIntfProfileKey@@YAKPEAX00@Z`
- size: `1014`
- prototype: `unsigned int __fastcall(void *, void *, void *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x180015ff0`

## callees

- `0x1800045b8`
- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x18000d5e4`
- `0x18000e620`
- `0x1800125b0`
- `0x180013bc0`
- `0x180014998`
- `0x1800169c0`
- `0x180016a08`
- `0x18001d370`
- `0x1800328b0`
- `0x180038518`
- `0x180038914`
- `0x180038a7c`
- `0x1800558c0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180038733`
- `MobileNetworking!ReleaseWriteLock` at `0x180038899`
- `MobileNetworking!ReleaseWriteLock` at `0x180038733`
- `MobileNetworking!ReleaseWriteLock` at `0x180038899`

## string_xrefs

- `0x180038729`: `UpdateIntfProfileKey`
- `0x18003875a`: `UpdateIntfProfileKey`
- `0x18003888f`: `UpdateIntfProfileKey`
- `0x1800388bd`: `UpdateIntfProfileKey`

## pseudocode

```c
__int64 __fastcall UpdateIntfProfileKey(void *a1, void *a2, void *a3)
{
  unsigned int v6; // eax
  struct MSMSEC_INTF_CONTEXT *v7; // rsi
  unsigned int v8; // ebx
  int v9; // r15d
  PVOID *v10; // r11
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  unsigned int v16; // r10d
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r11
  __int64 v20; // r8
  char v21; // r10
  unsigned int v22; // ecx
  unsigned int (*v23)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE **); // rdi
  void (*v24)(void *); // rbx
  int v25; // r13d
  unsigned int v26; // eax
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v27; // rdi
  __int64 v28; // rdx
  unsigned int (*v29)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int); // r9
  char v30; // cl
  struct MSMSEC_INTF_CONTEXT *v32; // [rsp+40h] [rbp-28h] BYREF
  _OWORD v33[2]; // [rsp+48h] [rbp-20h] BYREF
  struct DOT11_MSMSEC_CONNECTION_PROFILE *v34; // [rsp+C8h] [rbp+60h] BYREF

  v32 = 0;
  v33[0] = 0;
  v34 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
  v6 = SecMgrValidateRefAndLockAdapter(a2, &v32);
  v7 = v32;
  v8 = v6;
  if ( v6 )
  {
    v9 = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v11 = 45;
LABEL_8:
      WPP_SF_d(v10[7], v11, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v6);
LABEL_9:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_34;
    }
    goto LABEL_34;
  }
  v9 = 1;
  if ( *((void **)v32 + 328) != a3 )
  {
    v8 = 5023;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids);
      goto LABEL_9;
    }
    goto LABEL_34;
  }
  if ( !(unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v32 + 681), 13) )
  {
    v8 = 5023;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v15 = IntfActionStr(13, v12, v13, v14);
      v18 = IntfSecStateStr(v16, v17, v15);
      WPP_SF_SLSL(
        *(_QWORD *)(v19 + 56),
        47,
        (unsigned int)&WPP_b56916f94f50376d7382066de30fa1b3_Traceguids,
        v18,
        v21,
        v20,
        13);
      goto LABEL_9;
    }
    goto LABEL_34;
  }
  *((_DWORD *)v7 + 700) = 0;
  v6 = CopyRawData(*((_QWORD *)v7 + 349) + 64LL, v33);
  v8 = v6;
  if ( !v6 )
  {
    v22 = *((_DWORD *)v7 + 624);
    v23 = (unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE **))*((_QWORD *)v7 + 267);
    v24 = (void (*)(void *))*((_QWORD *)v7 + 263);
    v32 = (struct MSMSEC_INTF_CONTEXT *)*((_QWORD *)v7 + 266);
    v25 = **((_DWORD **)v7 + 349);
    TraceAdapterId(v22, "<<< Unlocking <<<");
    ReleaseWriteLock(v7, (char *)v7 + 2512, "UpdateIntfProfileKey", 413);
    v9 = 0;
    TraceAdapterId(*((_DWORD *)v7 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v7, "UpdateIntfProfileKey", 415);
    v26 = MSMGetConnectionProfile(a1, a3, &v34, v23, v24);
    v27 = v34;
    v8 = v26;
    if ( v26 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v28 = 49;
LABEL_30:
        WPP_SF_d(v10[7], v28, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v8);
        goto LABEL_31;
      }
    }
    else
    {
      FreeRawData((char *)v34 + 64);
      v29 = (unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int))v32;
      *((_QWORD *)v27 + 9) = *((_QWORD *)&v33[0] + 1);
      *((_DWORD *)v27 + 16) = v33[0];
      v30 = v25 ^ *(_DWORD *)v27;
      *((_QWORD *)&v33[0] + 1) = 0;
      LODWORD(v33[0]) = 0;
      *(_DWORD *)v27 ^= v30 & 2 ^ ((unsigned __int8)v25 ^ *(_BYTE *)v27 ^ v30 & 2) & 1;
      v8 = MSMSetConnectionProfile(a1, a3, v27, v29);
      if ( !v8 )
      {
LABEL_31:
        v10 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_32;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v28 = 50;
        goto LABEL_30;
      }
    }
LABEL_32:
    if ( v27 )
    {
      FreeMSMSecConfig(&v34);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_34;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v11 = 48;
    goto LABEL_8;
  }
LABEL_34:
  if ( *((_QWORD *)&v33[0] + 1) )
  {
    FreeMSMSecMemory((char *)v33 + 8);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    TraceAdapterId(*((_DWORD *)v7 + 624), "<<< Unlocking <<<");
    ReleaseWriteLock(v7, (char *)v7 + 2512, "UpdateIntfProfileKey", 444);
    TraceAdapterId(*((_DWORD *)v7 + 624), "<<< Derefing <<<");
    SecMgrDerefAdapterEx(v7, "UpdateIntfProfileKey", 448);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    WPP_SF_d(v10[7], 51, &WPP_b56916f94f50376d7382066de30fa1b3_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180038518  push    rbp
0x18003851a  push    rbx
0x18003851b  push    rsi
0x18003851c  push    rdi
0x18003851d  push    r12
0x18003851f  push    r13
0x180038521  push    r14
0x180038523  push    r15
0x180038525  mov     rbp, rsp
0x180038528  sub     rsp, 68h
0x18003852c  xorps   xmm0, xmm0
0x18003852f  mov     [rbp+var_28], 0
0x180038537  movups  [rbp+var_20], xmm0
0x18003853b  mov     r14, r8
0x18003853e  mov     [rbp+arg_18], 0
0x180038546  mov     rbx, rdx
0x180038549  mov     r12, rcx
0x18003854c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038553  lea     rdi, WPP_GLOBAL_Control
0x18003855a  cmp     rcx, rdi
0x18003855d  jz      short loc_18003857D
0x18003855f  test    dword ptr [rcx+44h], 100h
0x180038566  jz      short loc_18003857D
0x180038568  mov     rcx, [rcx+38h]
0x18003856c  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180038573  mov     edx, 2Ch ; ','
0x180038578  call    WPP_SF_
0x18003857d  lea     rdx, [rbp+var_28]; struct MSMSEC_INTF_CONTEXT **
0x180038581  mov     rcx, rbx; void *
0x180038584  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x180038589  mov     rsi, [rbp+var_28]
0x18003858d  mov     ebx, eax
0x18003858f  test    eax, eax
0x180038591  jz      short loc_1800385D4
0x180038593  xor     r15d, r15d
0x180038596  mov     r11, cs:WPP_GLOBAL_Control
0x18003859d  cmp     r11, rdi
0x1800385a0  jz      loc_180038854
0x1800385a6  test    byte ptr [r11+44h], 1
0x1800385ab  jz      loc_180038854
0x1800385b1  lea     edx, [r15+2Dh]
0x1800385b5  mov     rcx, [r11+38h]
0x1800385b9  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800385c0  mov     r9d, eax
0x1800385c3  call    WPP_SF_d
0x1800385c8  mov     r11, cs:WPP_GLOBAL_Control
0x1800385cf  jmp     loc_180038854
0x1800385d4  mov     rax, [rsi+0A40h]
0x1800385db  mov     r15d, 1
0x1800385e1  cmp     rax, r14
0x1800385e4  jz      short loc_180038623
0x1800385e6  mov     ebx, 139Fh
0x1800385eb  mov     r11, cs:WPP_GLOBAL_Control
0x1800385f2  cmp     r11, rdi
0x1800385f5  jz      loc_180038854
0x1800385fb  test    [r11+44h], r15b
0x1800385ff  jz      loc_180038854
0x180038605  mov     rcx, [r11+38h]
0x180038609  lea     edx, [r15+2Dh]
0x18003860d  mov     r9, r14
0x180038610  mov     [rsp+68h+var_48], rax
0x180038615  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x18003861c  call    WPP_SF_qq
0x180038621  jmp     short loc_1800385C8
0x180038623  mov     ecx, [rsi+0AA4h]
0x180038629  mov     r13d, 0Dh
0x18003862f  mov     edx, r13d
0x180038632  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180038637  test    eax, eax
0x180038639  jnz     short loc_18003869F
0x18003863b  mov     ebx, 139Fh
0x180038640  mov     r11, cs:WPP_GLOBAL_Control
0x180038647  cmp     r11, rdi
0x18003864a  jz      loc_180038854
0x180038650  test    [r11+44h], r15b
0x180038654  jz      loc_180038854
0x18003865a  mov     r10d, [rsi+0AA4h]
0x180038661  mov     ecx, r13d
0x180038664  call    ?IntfActionStr@@YAPEBGW4SECMGR_INTF_ACTION@@@Z; IntfActionStr(SECMGR_INTF_ACTION)
0x180038669  mov     ecx, r10d
0x18003866c  mov     r8, rax
0x18003866f  call    ?IntfSecStateStr@@YAPEBGW4MSMSEC_INTF_SEC_STATE@@@Z; IntfSecStateStr(MSMSEC_INTF_SEC_STATE)
0x180038674  mov     rcx, [r11+38h]
0x180038678  lea     edx, [r13+22h]
0x18003867c  mov     [rsp+68h+var_38], r13d
0x180038681  mov     r9, rax
0x180038684  mov     [rsp+68h+var_40], r8
0x180038689  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180038690  mov     dword ptr [rsp+68h+var_48], r10d
0x180038695  call    WPP_SF_SLSL
0x18003869a  jmp     loc_1800385C8
0x18003869f  mov     dword ptr [rsi+0AF0h], 0
0x1800386a9  lea     rdx, [rbp+var_20]
0x1800386ad  mov     rcx, [rsi+0AE8h]
0x1800386b4  add     rcx, 40h ; '@'
0x1800386b8  call    CopyRawData
0x1800386bd  mov     ebx, eax
0x1800386bf  test    eax, eax
0x1800386c1  jz      short loc_1800386E7
0x1800386c3  mov     r11, cs:WPP_GLOBAL_Control
0x1800386ca  cmp     r11, rdi
0x1800386cd  jz      loc_180038854
0x1800386d3  test    [r11+44h], r15b
0x1800386d7  jz      loc_180038854
0x1800386dd  mov     edx, 30h ; '0'
0x1800386e2  jmp     loc_1800385B5
0x1800386e7  mov     rax, [rsi+850h]
0x1800386ee  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x1800386f5  mov     ecx, [rsi+9C0h]; unsigned int
0x1800386fb  mov     rdi, [rsi+858h]
0x180038702  mov     rbx, [rsi+838h]
0x180038709  mov     [rbp+var_28], rax
0x18003870d  mov     rax, [rsi+0AE8h]
0x180038714  mov     r13d, [rax]
0x180038717  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x18003871c  lea     rdx, [rsi+9D0h]
0x180038723  mov     r9d, 19Dh
0x180038729  lea     r8, aUpdateintfprof; "UpdateIntfProfileKey"
0x180038730  mov     rcx, rsi
0x180038733  call    cs:__imp_ReleaseWriteLock
0x18003873a  nop     dword ptr [rax+rax+00h]
0x18003873f  mov     ecx, [rsi+9C0h]; unsigned int
0x180038745  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18003874c  xor     r15d, r15d
0x18003874f  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180038754  mov     r8d, 19Fh; int
0x18003875a  lea     rdx, aUpdateintfprof; "UpdateIntfProfileKey"
0x180038761  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180038764  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180038769  mov     r9, rdi; unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE **)
0x18003876c  mov     [rsp+68h+var_48], rbx; void (*)(void *)
0x180038771  lea     r8, [rbp+arg_18]; struct DOT11_MSMSEC_CONNECTION_PROFILE **
0x180038775  mov     rdx, r14; void *
0x180038778  mov     rcx, r12; void *
0x18003877b  call    ?MSMGetConnectionProfile@@YAKPEAX0PEAPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@P6AK001@ZP6AX0@Z@Z; MSMGetConnectionProfile(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE * *,ulong (*)(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE * *),void (*)(void *))
0x180038780  mov     rdi, [rbp+arg_18]
0x180038784  mov     ebx, eax
0x180038786  test    eax, eax
0x180038788  jz      short loc_1800387B2
0x18003878a  mov     r11, cs:WPP_GLOBAL_Control
0x180038791  lea     rax, WPP_GLOBAL_Control
0x180038798  cmp     r11, rax
0x18003879b  jz      loc_180038838
0x1800387a1  test    byte ptr [r11+44h], 1
0x1800387a6  jz      loc_180038838
0x1800387ac  lea     edx, [r15+31h]
0x1800387b0  jmp     short loc_18003881E
0x1800387b2  lea     rcx, [rdi+40h]
0x1800387b6  call    FreeRawData
0x1800387bb  mov     rax, qword ptr [rbp+var_20+8]
0x1800387bf  mov     r8, rdi; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x1800387c2  mov     r9, [rbp+var_28]; unsigned int (*)(void *, void *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, int)
0x1800387c6  mov     rdx, r14; void *
0x1800387c9  mov     [rdi+48h], rax
0x1800387cd  mov     eax, dword ptr [rbp+var_20]
0x1800387d0  mov     [rdi+40h], eax
0x1800387d3  mov     ecx, [rdi]
0x1800387d5  xor     ecx, r13d
0x1800387d8  mov     qword ptr [rbp+var_20+8], r15
0x1800387dc  and     ecx, 2
0x1800387df  mov     dword ptr [rbp+var_20], r15d
0x1800387e3  xor     ecx, [rdi]
0x1800387e5  mov     eax, ecx
0x1800387e7  xor     eax, r13d
0x1800387ea  and     eax, 1
0x1800387ed  xor     eax, ecx
0x1800387ef  mov     rcx, r12; void *
0x1800387f2  mov     [rdi], eax
0x1800387f4  call    ?MSMSetConnectionProfile@@YAKPEAX0PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@P6AK001H@Z@Z; MSMSetConnectionProfile(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,ulong (*)(void *,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,int))
0x1800387f9  mov     ebx, eax
0x1800387fb  test    eax, eax
0x1800387fd  jz      short loc_180038831
0x1800387ff  mov     r11, cs:WPP_GLOBAL_Control
0x180038806  lea     rax, WPP_GLOBAL_Control
0x18003880d  cmp     r11, rax
0x180038810  jz      short loc_180038838
0x180038812  test    byte ptr [r11+44h], 1
0x180038817  jz      short loc_180038838
0x180038819  mov     edx, 32h ; '2'
0x18003881e  mov     rcx, [r11+38h]
0x180038822  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x180038829  mov     r9d, ebx
0x18003882c  call    WPP_SF_d
0x180038831  mov     r11, cs:WPP_GLOBAL_Control
0x180038838  test    rdi, rdi
0x18003883b  jz      short loc_18003884D
0x18003883d  lea     rcx, [rbp+arg_18]
0x180038841  call    FreeMSMSecConfig
0x180038846  mov     r11, cs:WPP_GLOBAL_Control
0x18003884d  lea     rdi, WPP_GLOBAL_Control
0x180038854  cmp     qword ptr [rbp+var_20+8], 0
0x180038859  jz      short loc_18003886B
0x18003885b  lea     rcx, [rbp+var_20+8]
0x18003885f  call    FreeMSMSecMemory
0x180038864  mov     r11, cs:WPP_GLOBAL_Control
0x18003886b  test    r15d, r15d
0x18003886e  jz      short loc_1800388D3
0x180038870  mov     ecx, [rsi+9C0h]; unsigned int
0x180038876  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x18003887d  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180038882  lea     rdx, [rsi+9D0h]
0x180038889  mov     r9d, 1BCh
0x18003888f  lea     r8, aUpdateintfprof; "UpdateIntfProfileKey"
0x180038896  mov     rcx, rsi
0x180038899  call    cs:__imp_ReleaseWriteLock
0x1800388a0  nop     dword ptr [rax+rax+00h]
0x1800388a5  mov     ecx, [rsi+9C0h]; unsigned int
0x1800388ab  lea     rdx, aDerefing; "<<< Derefing <<<"
0x1800388b2  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800388b7  mov     r8d, 1C0h; int
0x1800388bd  lea     rdx, aUpdateintfprof; "UpdateIntfProfileKey"
0x1800388c4  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x1800388c7  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x1800388cc  mov     r11, cs:WPP_GLOBAL_Control
0x1800388d3  cmp     r11, rdi
0x1800388d6  jz      short loc_1800388FA
0x1800388d8  test    dword ptr [r11+44h], 100h
0x1800388e0  jz      short loc_1800388FA
0x1800388e2  mov     rcx, [r11+38h]
0x1800388e6  lea     r8, WPP_b56916f94f50376d7382066de30fa1b3_Traceguids
0x1800388ed  mov     edx, 33h ; '3'
0x1800388f2  mov     r9d, ebx
0x1800388f5  call    WPP_SF_d
0x1800388fa  mov     eax, ebx
0x1800388fc  add     rsp, 68h
0x180038900  pop     r15
0x180038902  pop     r14
0x180038904  pop     r13
0x180038906  pop     r12
0x180038908  pop     rdi
0x180038909  pop     rsi
0x18003890a  pop     rbx
0x18003890b  pop     rbp
0x18003890c  retn
```
