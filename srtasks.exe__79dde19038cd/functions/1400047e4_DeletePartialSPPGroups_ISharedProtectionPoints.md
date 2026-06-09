# _DeletePartialSPPGroups(ISharedProtectionPoints *)

- ea: `0x1400047e4`
- end: `0x140004a67`
- name: `?_DeletePartialSPPGroups@@YAJPEAUISharedProtectionPoints@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(struct ISharedProtectionPoints *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140004a70`

## callees

- `0x140002e1c`
- `0x1400047e4`
- `0x1400055cc`
- `0x14000d1a4`
- `0x14000d688`
- `0x14000e0f0`
- `0x14000e324`
- `0x14000e41c`
- `0x14001094e`
- `0x140010980`
- `0x140011010`

## import_xrefs

- `SPP!SppFreeGroupPropArray` at `0x140004a29`
- `SPP!SppFreeGroupPropArray` at `0x140004a29`

## string_xrefs

- `0x14000484a`: `_DeletePartialSPPGroups`

## pseudocode

```c
__int64 __fastcall _DeletePartialSPPGroups(struct ISharedProtectionPoints *a1)
{
  __int64 (__fastcall *v2)(struct ISharedProtectionPoints *, _QWORD, GUID *); // rax
  __int16 v3; // ax
  __int64 v4; // r8
  __int64 v5; // rdi
  __int128 *v6; // rbx
  int v7; // edx
  int v8; // eax
  __int64 (__fastcall *v9)(struct ISharedProtectionPoints *, __int128 *); // rax
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  __int16 i; // [rsp+34h] [rbp-CCh]
  __int16 v16; // [rsp+36h] [rbp-CAh]
  __int128 v17; // [rsp+70h] [rbp-90h] BYREF
  GUID v18; // [rsp+80h] [rbp-80h] BYREF
  int v19; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v20[156]; // [rsp+94h] [rbp-6Ch] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "_DeletePartialSPPGroups", 0x81u, 1u);
  v12 = 0;
  v13 = 0;
  v19 = 0;
  memset_0(v20, 0, 0x94u);
  v2 = *(__int64 (__fastcall **)(struct ISharedProtectionPoints *, _QWORD, GUID *))(*(_QWORD *)a1 + 104LL);
  v18 = GUID_NULL;
  v14 = v2(a1, 0, &v18);
  v3 = 139;
  if ( v14 < 0
    || (i = 139,
        v14 = (*(__int64 (__fastcall **)(struct ISharedProtectionPoints *, unsigned int *, __int64 *))(*(_QWORD *)a1 + 64LL))(
                a1,
                &v12,
                &v13),
        v3 = 140,
        v14 < 0) )
  {
LABEL_23:
    v16 = v3;
    goto LABEL_24;
  }
  v5 = 0;
  for ( i = 140; (unsigned int)v5 < v12; v5 = (unsigned int)(v5 + 1) )
  {
    v6 = (__int128 *)(v13 + 144 * v5);
    if ( *(_OWORD *)&v18 == *(__int128 *)((char *)v6 + 40) )
    {
      Free_SR_RP_PROP((struct _SR_RP_PROP *)&v19);
      v14 = SrConvertSppGroupToSrRpProp(1, v6, &v19);
      v3 = 156;
      if ( v14 < 0 )
        goto LABEL_23;
      i = 156;
      v8 = SrValidateRestorePoint((const struct _SR_RP_PROP *)&v19, v7);
      v14 = v8;
      if ( v8 < 0 )
      {
        v16 = 158;
        break;
      }
      i = 158;
      if ( v8 == 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
        {
          WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, v4, v6);
        }
        v9 = *(__int64 (__fastcall **)(struct ISharedProtectionPoints *, __int128 *))(*(_QWORD *)a1 + 56LL);
        v17 = *v6;
        v14 = v9(a1, &v17);
        if ( v14 < 0 )
        {
          v16 = 167;
          break;
        }
        i = 167;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v4, v13 + 144 * v5);
    }
  }
LABEL_24:
  Free_SR_RP_PROP((struct _SR_RP_PROP *)&v19);
  SppFreeGroupPropArray(v12, &v13);
  v10 = v14;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return v10;
}

```

## disassembly

```asm
0x1400047e4  mov     [rsp-8+arg_8], rbx
0x1400047e9  mov     [rsp-8+arg_10], rsi
0x1400047ee  push    rbp
0x1400047ef  push    rdi
0x1400047f0  push    r12
0x1400047f2  push    r13
0x1400047f4  push    r15
0x1400047f6  lea     rbp, [rsp-40h]
0x1400047fb  sub     rsp, 140h
0x140004802  mov     rax, cs:__security_cookie
0x140004809  xor     rax, rsp
0x14000480c  mov     [rbp+60h+var_30], rax
0x140004810  mov     rsi, rcx
0x140004813  mov     rcx, cs:WPP_GLOBAL_Control
0x14000481a  lea     r15, WPP_GLOBAL_Control
0x140004821  cmp     rcx, r15
0x140004824  jz      short loc_140004844
0x140004826  test    dword ptr [rcx+1Ch], 20000000h
0x14000482d  jz      short loc_140004844
0x14000482f  mov     rcx, [rcx+10h]
0x140004833  lea     r8, WPP_101e0a96400b3b07d1faa29ced9d8670_Traceguids
0x14000483a  mov     edx, 0Fh
0x14000483f  call    WPP_SF_
0x140004844  mov     r9d, 1; unsigned __int16
0x14000484a  lea     rdx, aDeletepartials; "_DeletePartialSPPGroups"
0x140004851  mov     r8d, 81h; unsigned __int16
0x140004857  lea     rcx, [rsp+160h+var_130]; this
0x14000485c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140004861  xor     edx, edx; Val
0x140004863  mov     [rsp+160h+var_140], 0
0x14000486b  mov     r8d, 94h; Size
0x140004871  mov     [rsp+160h+var_138], 0
0x14000487a  lea     rcx, [rbp+60h+var_CC]; void *
0x14000487e  mov     [rbp+60h+var_D0], 0
0x140004885  call    memset_0
0x14000488a  mov     rax, [rsi]
0x14000488d  lea     r8, [rbp+60h+var_E0]
0x140004891  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140004898  xor     edx, edx
0x14000489a  mov     rcx, rsi
0x14000489d  mov     rax, [rax+68h]
0x1400048a1  movdqu  [rbp+60h+var_E0], xmm0
0x1400048a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048ab  mov     [rsp+160h+var_130], eax
0x1400048af  test    eax, eax
0x1400048b1  mov     eax, 8Bh
0x1400048b6  js      loc_140004A12
0x1400048bc  mov     [rsp+160h+var_12C], ax
0x1400048c1  lea     r8, [rsp+160h+var_138]
0x1400048c6  mov     rax, [rsi]
0x1400048c9  lea     rdx, [rsp+160h+var_140]
0x1400048ce  mov     rcx, rsi
0x1400048d1  mov     rax, [rax+40h]
0x1400048d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048da  mov     [rsp+160h+var_130], eax
0x1400048de  test    eax, eax
0x1400048e0  mov     eax, 8Ch
0x1400048e5  js      loc_140004A12
0x1400048eb  xor     edi, edi
0x1400048ed  mov     [rsp+160h+var_12C], ax
0x1400048f2  cmp     [rsp+160h+var_140], edi
0x1400048f6  jbe     loc_140004A17
0x1400048fc  lea     r13d, [rax+12h]
0x140004900  lea     r12d, [rax+1Bh]
0x140004904  mov     rax, qword ptr [rbp+60h+var_E0]
0x140004908  lea     rbx, [rdi+rdi*8]
0x14000490c  shl     rbx, 4
0x140004910  add     rbx, [rsp+160h+var_138]
0x140004915  cmp     rax, [rbx+28h]
0x140004919  jnz     loc_1400049CE
0x14000491f  mov     rax, qword ptr [rbp+60h+var_E0+8]
0x140004923  cmp     rax, [rbx+30h]
0x140004927  jnz     loc_1400049CE
0x14000492d  lea     rcx, [rbp+60h+var_D0]; struct _SR_RP_PROP *
0x140004931  call    ?Free_SR_RP_PROP@@YAXPEAU_SR_RP_PROP@@@Z; Free_SR_RP_PROP(_SR_RP_PROP *)
0x140004936  lea     r8, [rbp+60h+var_D0]
0x14000493a  mov     rdx, rbx
0x14000493d  mov     ecx, 1
0x140004942  call    ?SrConvertSppGroupToSrRpProp@@YAJW4_SR_RESTORE_SOURCE@@PEBU_SPP_GROUP_PROP@@PEAU_SR_RP_PROP@@@Z; SrConvertSppGroupToSrRpProp(_SR_RESTORE_SOURCE,_SPP_GROUP_PROP const *,_SR_RP_PROP *)
0x140004947  mov     [rsp+160h+var_130], eax
0x14000494b  test    eax, eax
0x14000494d  mov     eax, 9Ch
0x140004952  js      loc_140004A12
0x140004958  lea     rcx, [rbp+60h+var_D0]; struct _SR_RP_PROP *
0x14000495c  mov     [rsp+160h+var_12C], ax
0x140004961  call    ?SrValidateRestorePoint@@YAJPEBU_SR_RP_PROP@@H@Z; SrValidateRestorePoint(_SR_RP_PROP const *,int)
0x140004966  mov     [rsp+160h+var_130], eax
0x14000496a  test    eax, eax
0x14000496c  js      loc_140004A0A
0x140004972  mov     [rsp+160h+var_12C], r13w
0x140004978  cmp     eax, 1
0x14000497b  jnz     short loc_1400049F4
0x14000497d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004984  cmp     rcx, r15
0x140004987  jz      short loc_1400049A1
0x140004989  test    dword ptr [rcx+1Ch], 8000000h
0x140004990  jz      short loc_1400049A1
0x140004992  mov     rcx, [rcx+10h]
0x140004996  lea     edx, [rax+10h]
0x140004999  mov     r9, rbx
0x14000499c  call    WPP_SF__guid_
0x1400049a1  mov     rax, [rsi]
0x1400049a4  lea     rdx, [rsp+160h+var_F0]
0x1400049a9  movups  xmm0, xmmword ptr [rbx]
0x1400049ac  mov     rcx, rsi
0x1400049af  mov     rax, [rax+38h]
0x1400049b3  movdqu  [rsp+160h+var_F0], xmm0
0x1400049b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049be  mov     [rsp+160h+var_130], eax
0x1400049c2  test    eax, eax
0x1400049c4  js      short loc_140004A02
0x1400049c6  mov     [rsp+160h+var_12C], r12w
0x1400049cc  jmp     short loc_1400049F4
0x1400049ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400049d5  cmp     rcx, r15
0x1400049d8  jz      short loc_1400049F4
0x1400049da  test    dword ptr [rcx+1Ch], 8000000h
0x1400049e1  jz      short loc_1400049F4
0x1400049e3  mov     rcx, [rcx+10h]
0x1400049e7  mov     edx, 10h
0x1400049ec  mov     r9, rbx
0x1400049ef  call    WPP_SF__guid_
0x1400049f4  inc     edi
0x1400049f6  cmp     edi, [rsp+160h+var_140]
0x1400049fa  jb      loc_140004904
0x140004a00  jmp     short loc_140004A17
0x140004a02  mov     [rsp+160h+var_12A], r12w
0x140004a08  jmp     short loc_140004A17
0x140004a0a  mov     [rsp+160h+var_12A], r13w
0x140004a10  jmp     short loc_140004A17
0x140004a12  mov     [rsp+160h+var_12A], ax
0x140004a17  lea     rcx, [rbp+60h+var_D0]; struct _SR_RP_PROP *
0x140004a1b  call    ?Free_SR_RP_PROP@@YAXPEAU_SR_RP_PROP@@@Z; Free_SR_RP_PROP(_SR_RP_PROP *)
0x140004a20  mov     ecx, [rsp+160h+var_140]
0x140004a24  lea     rdx, [rsp+160h+var_138]
0x140004a29  call    cs:__imp_SppFreeGroupPropArray
0x140004a2f  mov     ebx, [rsp+160h+var_130]
0x140004a33  lea     rcx, [rsp+160h+var_130]; this
0x140004a38  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140004a3d  mov     eax, ebx
0x140004a3f  mov     rcx, [rbp+60h+var_30]
0x140004a43  xor     rcx, rsp; StackCookie
0x140004a46  call    __security_check_cookie
0x140004a4b  lea     r11, [rsp+160h+var_20]
0x140004a53  mov     rbx, [r11+38h]
0x140004a57  mov     rsi, [r11+40h]
0x140004a5b  mov     rsp, r11
0x140004a5e  pop     r15
0x140004a60  pop     r13
0x140004a62  pop     r12
0x140004a64  pop     rdi
0x140004a65  pop     rbp
0x140004a66  retn
```
