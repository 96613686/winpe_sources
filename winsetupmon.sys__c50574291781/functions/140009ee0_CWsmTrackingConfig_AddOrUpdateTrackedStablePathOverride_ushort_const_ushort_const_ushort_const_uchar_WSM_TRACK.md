# CWsmTrackingConfig::AddOrUpdateTrackedStablePathOverride(ushort const *,ushort const *,ushort const *,uchar,_WSM_TRACKING_MODE)

- ea: `0x140009ee0`
- end: `0x14000a0f3`
- name: `?AddOrUpdateTrackedStablePathOverride@CWsmTrackingConfig@@UEAAJPEBG00EW4_WSM_TRACKING_MODE@@@Z`
- size: `531`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x140008b00`
- `0x140009018`
- `0x140009b70`
- `0x140009ee0`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000f684`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009f85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009f85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009faf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a0d1`
- `ntoskrnl!_wcsicmp` at `0x140009fe9`
- `ntoskrnl!_wcsicmp` at `0x140009fe9`

## string_xrefs

- `0x14000a07e`: `CWsmTrackingConfig::AddOrUpdateTrackedStablePathOverride: Failed to update configuration (with override info added) (0x%08X)`
- `0x14000a070`: `CWsmTrackingConfig::AddOrUpdateTrackedStablePathOverride: Failed to read configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::AddOrUpdateTrackedStablePathOverride(
        CWsmTrackingConfig *a1,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        int a6)
{
  __int64 (__fastcall **v8)(CWsmTrackingConfig *); // rax
  struct CWsmTrackingConfig::CTrackingConfig **v9; // rbx
  struct _WSM_TRACKING_CONFIG *v10; // rax
  int Instance; // r14d
  CWsmTrackingConfig::CTrackingConfig *v12; // rbx
  PVOID v13; // rbx
  _QWORD *v14; // r14
  char v15; // r13
  __int64 v16; // r15
  __int64 v17; // r9
  int updated; // ebx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int128 v21; // xmm0
  __int64 v22; // xmm1_8
  __int64 v23; // rcx
  PVOID v24; // rsi
  PVOID P; // [rsp+30h] [rbp-20h] BYREF
  CWsmTrackingConfig::CTrackingConfig *v26; // [rsp+38h] [rbp-18h] BYREF
  CWsmTrackingConfig::CTrackingConfig **v27; // [rsp+40h] [rbp-10h]

  if ( !a2 )
    return 3221225485LL;
  v8 = *(__int64 (__fastcall ***)(CWsmTrackingConfig *))a1;
  P = 0;
  if ( !(*v8)(a1) )
    return 3221225530LL;
  v9 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                        &v26,
                                                        &P);
  v10 = (struct _WSM_TRACKING_CONFIG *)(**(__int64 (__fastcall ***)(CWsmTrackingConfig *))a1)(a1);
  Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(v10, 1, v9);
  if ( v26 )
  {
    v12 = *v27;
    *v27 = v26;
    if ( v12 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v12);
      ExFreePoolWithTag(v12, 0x6E6D7377u);
    }
  }
  if ( Instance >= 0 )
  {
    v14 = P;
    v15 = 0;
    v16 = 0;
    if ( !*((_DWORD *)P + 26) )
      goto LABEL_19;
    do
    {
      if ( !_wcsicmp(*(const wchar_t **)(v14[14] + 24 * v16), a2) )
      {
        LOBYTE(v17) = a5;
        updated = CWsmTrackingConfig::CTrackingPathInfo::AddOrUpdateTrackedStablePathOverride(
                    *(_QWORD *)(v14[1] + 8 * v16),
                    a3,
                    a4,
                    v17,
                    a6);
        if ( updated < 0 )
          goto LABEL_20;
        v15 = 1;
        v19 = *(_QWORD *)(v14[1] + 8 * v16);
        v20 = v14[4];
        v21 = *(_OWORD *)(v19 + 72);
        v22 = *(_QWORD *)(v19 + 88);
        v23 = 3 * v16;
        *(_OWORD *)(v20 + 8 * v23) = v21;
        *(_QWORD *)(v20 + 8 * v23 + 16) = v22;
      }
      v16 = (unsigned int)(v16 + 1);
    }
    while ( (unsigned int)v16 < *((_DWORD *)v14 + 26) );
    if ( v15 )
    {
      updated = CWsmTrackingConfig::Read(a1, (struct _WSM_TRACKING_CONFIG *const)((char *)P + 88), 1);
      if ( updated < 0 )
        WriteLog(
          0,
          "CWsmTrackingConfig::AddOrUpdateTrackedStablePathOverride: Failed to read configuration (0x%08X)",
          (unsigned int)updated);
    }
    else
    {
LABEL_19:
      updated = -1073741766;
LABEL_20:
      WriteLog(
        0,
        "CWsmTrackingConfig::AddOrUpdateTrackedStablePathOverride: Failed to update configuration (with override info added) (0x%08X)",
        (unsigned int)updated);
    }
    v24 = P;
    if ( P )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
      ExFreePoolWithTag(v24, 0x6E6D7377u);
    }
    return (unsigned int)updated;
  }
  else
  {
    v13 = P;
    if ( P )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
      ExFreePoolWithTag(v13, 0x6E6D7377u);
    }
    return (unsigned int)Instance;
  }
}

```

## disassembly

```asm
0x140009ee0  mov     [rsp-38h+arg_18], r9
0x140009ee5  mov     [rsp-38h+arg_10], r8
0x140009eea  mov     [rsp-38h+Str2], rdx
0x140009eef  push    rbp
0x140009ef0  push    rbx
0x140009ef1  push    rsi
0x140009ef2  push    r12
0x140009ef4  push    r13
0x140009ef6  push    r14
0x140009ef8  push    r15
0x140009efa  mov     rbp, rsp
0x140009efd  sub     rsp, 50h
0x140009f01  mov     rsi, rcx
0x140009f04  test    rdx, rdx
0x140009f07  jnz     short loc_140009F13
0x140009f09  mov     eax, 0C000000Dh
0x140009f0e  jmp     loc_14000A0E2
0x140009f13  mov     rax, [rcx]
0x140009f16  mov     [rbp+P], 0
0x140009f1e  mov     rax, [rax]
0x140009f21  call    _guard_dispatch_icall
0x140009f26  test    rax, rax
0x140009f29  jz      loc_14000A0B8
0x140009f2f  lea     rdx, [rbp+P]
0x140009f33  lea     rcx, [rbp+var_18]
0x140009f37  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x140009f3c  mov     rcx, [rsi]
0x140009f3f  mov     rbx, rax
0x140009f42  mov     rax, [rcx]
0x140009f45  mov     rcx, rsi
0x140009f48  call    _guard_dispatch_icall
0x140009f4d  mov     r8, rbx; struct CWsmTrackingConfig::CTrackingConfig **
0x140009f50  mov     dl, 1; bool
0x140009f52  mov     rcx, rax; struct _WSM_TRACKING_CONFIG *
0x140009f55  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x140009f5a  mov     r14d, eax
0x140009f5d  mov     rax, [rbp+var_18]
0x140009f61  test    rax, rax
0x140009f64  jz      short loc_140009F91
0x140009f66  mov     rdx, [rbp+var_10]
0x140009f6a  mov     rbx, [rdx]
0x140009f6d  mov     [rdx], rax
0x140009f70  test    rbx, rbx
0x140009f73  jz      short loc_140009F91
0x140009f75  mov     rcx, rbx; this
0x140009f78  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x140009f7d  mov     edx, 6E6D7377h; Tag
0x140009f82  mov     rcx, rbx; P
0x140009f85  call    cs:__imp_ExFreePoolWithTag
0x140009f8c  nop     dword ptr [rax+rax+00h]
0x140009f91  test    r14d, r14d
0x140009f94  jns     short loc_140009FC3
0x140009f96  mov     rbx, [rbp+P]
0x140009f9a  test    rbx, rbx
0x140009f9d  jz      short loc_140009FBB
0x140009f9f  mov     rcx, rbx; this
0x140009fa2  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x140009fa7  mov     edx, 6E6D7377h; Tag
0x140009fac  mov     rcx, rbx; P
0x140009faf  call    cs:__imp_ExFreePoolWithTag
0x140009fb6  nop     dword ptr [rax+rax+00h]
0x140009fbb  mov     eax, r14d
0x140009fbe  jmp     loc_14000A0E2
0x140009fc3  mov     r14, [rbp+P]
0x140009fc7  xor     ebx, ebx
0x140009fc9  xor     r13b, r13b
0x140009fcc  xor     r15d, r15d
0x140009fcf  cmp     [r14+68h], ebx
0x140009fd3  jbe     loc_14000A079
0x140009fd9  mov     rcx, [r14+70h]
0x140009fdd  lea     rax, [r15+r15*2]
0x140009fe1  mov     rdx, [rbp+Str2]; Str2
0x140009fe5  mov     rcx, [rcx+rax*8]; Str1
0x140009fe9  call    cs:__imp__wcsicmp
0x140009ff0  nop     dword ptr [rax+rax+00h]
0x140009ff5  test    eax, eax
0x140009ff7  jnz     short loc_14000A045
0x140009ff9  mov     rcx, [r14+8]
0x140009ffd  mov     eax, [rbp+arg_28]
0x14000a000  mov     r9b, [rbp+arg_20]
0x14000a004  mov     r8, [rbp+arg_18]
0x14000a008  mov     rcx, [rcx+r15*8]
0x14000a00c  mov     rdx, [rbp+arg_10]
0x14000a010  mov     [rsp+50h+var_30], eax
0x14000a014  call    ?AddOrUpdateTrackedStablePathOverride@CTrackingPathInfo@CWsmTrackingConfig@@QEAAJPEBG0EW4_WSM_TRACKING_MODE@@@Z; CWsmTrackingConfig::CTrackingPathInfo::AddOrUpdateTrackedStablePathOverride(ushort const *,ushort const *,uchar,_WSM_TRACKING_MODE)
0x14000a019  mov     ebx, eax
0x14000a01b  test    eax, eax
0x14000a01d  js      short loc_14000A07E
0x14000a01f  mov     rax, [r14+8]
0x14000a023  mov     r13b, 1
0x14000a026  mov     rcx, [rax+r15*8]
0x14000a02a  mov     rax, [r14+20h]
0x14000a02e  movups  xmm0, xmmword ptr [rcx+48h]
0x14000a032  movsd   xmm1, qword ptr [rcx+58h]
0x14000a037  lea     rcx, [r15+r15*2]
0x14000a03b  movups  xmmword ptr [rax+rcx*8], xmm0
0x14000a03f  movsd   qword ptr [rax+rcx*8+10h], xmm1
0x14000a045  inc     r15d
0x14000a048  cmp     r15d, [r14+68h]
0x14000a04c  jb      short loc_140009FD9
0x14000a04e  test    r13b, r13b
0x14000a051  jz      short loc_14000A079
0x14000a053  test    ebx, ebx
0x14000a055  js      short loc_14000A07E
0x14000a057  mov     rdx, [rbp+P]
0x14000a05b  mov     r8b, 1; bool
0x14000a05e  add     rdx, 58h ; 'X'; struct _WSM_TRACKING_CONFIG *
0x14000a062  mov     rcx, rsi; this
0x14000a065  call    ?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)
0x14000a06a  mov     ebx, eax
0x14000a06c  test    eax, eax
0x14000a06e  jns     short loc_14000A08F
0x14000a070  lea     rdx, aCwsmtrackingco_8; "CWsmTrackingConfig::AddOrUpdateTrackedS"...
0x14000a077  jmp     short loc_14000A085
0x14000a079  mov     ebx, 0C000003Ah
0x14000a07e  lea     rdx, aCwsmtrackingco_3; "CWsmTrackingConfig::AddOrUpdateTrackedS"...
0x14000a085  mov     r8d, ebx
0x14000a088  xor     ecx, ecx
0x14000a08a  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000a08f  mov     rsi, [rbp+P]
0x14000a093  test    rsi, rsi
0x14000a096  jz      short loc_14000A0B4
0x14000a098  mov     rcx, rsi; this
0x14000a09b  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000a0a0  mov     edx, 6E6D7377h; Tag
0x14000a0a5  mov     rcx, rsi; P
0x14000a0a8  call    cs:__imp_ExFreePoolWithTag
0x14000a0af  nop     dword ptr [rax+rax+00h]
0x14000a0b4  mov     eax, ebx
0x14000a0b6  jmp     short loc_14000A0E2
0x14000a0b8  mov     rbx, [rbp+P]
0x14000a0bc  test    rbx, rbx
0x14000a0bf  jz      short loc_14000A0DD
0x14000a0c1  mov     rcx, rbx; this
0x14000a0c4  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000a0c9  mov     edx, 6E6D7377h; Tag
0x14000a0ce  mov     rcx, rbx; P
0x14000a0d1  call    cs:__imp_ExFreePoolWithTag
0x14000a0d8  nop     dword ptr [rax+rax+00h]
0x14000a0dd  mov     eax, 0C000003Ah
0x14000a0e2  add     rsp, 50h
0x14000a0e6  pop     r15
0x14000a0e8  pop     r14
0x14000a0ea  pop     r13
0x14000a0ec  pop     r12
0x14000a0ee  pop     rsi
0x14000a0ef  pop     rbx
0x14000a0f0  pop     rbp
0x14000a0f1  retn
```
