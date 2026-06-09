# UtilIsNetworkRestricted(void)

- ea: `0x14001aec4`
- end: `0x14001b128`
- name: `?UtilIsNetworkRestricted@@YAHXZ`
- size: `612`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005f98`

## callees

- `0x14000e318`
- `0x14000e340`
- `0x14001852c`
- `0x14001aec4`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001af58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001af58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001af03`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001af96`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001af03`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001af96`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001afd5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001afd5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001b061`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001b061`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001b113`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001b113`

## string_xrefs

- `0x14001af4e`: `RtlGetCurrentServiceSessionId`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 UtilIsNetworkRestricted(void)
{
  HMODULE *v0; // rax
  HMODULE v1; // rbx
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  bool v4; // di
  unsigned int (*ProcAddress)(void); // rax
  unsigned int v7; // edi
  HRESULT v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  HRESULT v12; // esi
  LPVOID v13; // rcx
  int v14; // eax
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  LPVOID *v16; // [rsp+38h] [rbp-20h]
  int v17; // [rsp+90h] [rbp+38h] BYREF
  HMODULE v18; // [rsp+98h] [rbp+40h]
  __int64 v19; // [rsp+A0h] [rbp+48h] BYREF
  HMODULE hLibModule; // [rsp+A8h] [rbp+50h] BYREF

  v17 = 0;
  v18 = 0;
  v0 = (HMODULE *)UtilLoadModFromSystem(&hLibModule);
  v1 = *v0;
  *v0 = 0;
  v18 = v1;
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( !v1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v3 = 152;
LABEL_7:
    WPP_SF_(v2[2], v3, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    v2 = WPP_GLOBAL_Control;
LABEL_8:
    v4 = 0;
    goto LABEL_14;
  }
  ProcAddress = (unsigned int (*)(void))GetProcAddress(v1, "RtlGetCurrentServiceSessionId");
  if ( !ProcAddress )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v3 = 153;
    goto LABEL_7;
  }
  v4 = ProcAddress() != 0;
  v2 = WPP_GLOBAL_Control;
LABEL_14:
  if ( v1 )
  {
    FreeLibrary(v1);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
      WPP_SF_(v2[2], 28, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    return 0;
  }
  v7 = 0;
  v8 = CoInitializeEx(0, 0);
  LODWORD(v18) = v8;
  v19 = 0;
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147417850 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v10 = 29;
    v11 = (unsigned int)v8;
    goto LABEL_26;
  }
  ppv = 0;
  v16 = (LPVOID *)&v19;
  v19 = 0;
  v12 = CoCreateInstance(
          &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
          0,
          0x17u,
          &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b,
          &ppv);
  if ( ppv )
  {
    v13 = *v16;
    *v16 = ppv;
    if ( v13 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v12 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v10 = 30;
    v11 = (unsigned int)v12;
    goto LABEL_26;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)v19 + 24LL))(v19, &v17, 0);
  if ( v14 >= 0 )
  {
    if ( v17 && (v17 & 1) == 0 )
      v7 = 1;
    goto LABEL_41;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 31;
    v11 = (unsigned int)v14;
LABEL_26:
    WPP_SF_d(v9[2], v10, &WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v11);
  }
LABEL_41:
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v8 >= 0 )
    CoUninitialize();
  return v7;
}

```

## disassembly

```asm
0x14001aec4  push    rbp
0x14001aec6  push    rbx
0x14001aec7  push    rsi
0x14001aec8  push    rdi
0x14001aec9  push    r12
0x14001aecb  push    r15
0x14001aecd  mov     rbp, rsp
0x14001aed0  sub     rsp, 58h
0x14001aed4  mov     [rbp+arg_0], 0
0x14001aedb  mov     [rbp+arg_8], 0
0x14001aee3  lea     rcx, [rbp+hLibModule]
0x14001aee7  call    ?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z; UtilLoadModFromSystem(wchar_t const *)
0x14001aeec  mov     rbx, [rax]
0x14001aeef  mov     qword ptr [rax], 0
0x14001aef6  mov     [rbp+arg_8], rbx
0x14001aefa  mov     rcx, [rbp+hLibModule]; hLibModule
0x14001aefe  test    rcx, rcx
0x14001af01  jz      short loc_14001AF09
0x14001af03  call    cs:__imp_FreeLibrary
0x14001af09  lea     r12, WPP_GLOBAL_Control
0x14001af10  mov     r15d, 1
0x14001af16  test    rbx, rbx
0x14001af19  jnz     short loc_14001AF4E
0x14001af1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001af22  cmp     rcx, r12
0x14001af25  jz      short loc_14001AF49
0x14001af27  test    [rcx+1Ch], r15b
0x14001af2b  jz      short loc_14001AF49
0x14001af2d  mov     edx, 98h
0x14001af32  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001af39  mov     rcx, [rcx+10h]
0x14001af3d  call    WPP_SF_
0x14001af42  mov     rcx, cs:WPP_GLOBAL_Control
0x14001af49  xor     dil, dil
0x14001af4c  jmp     short loc_14001AF8E
0x14001af4e  lea     rdx, aRtlgetcurrents; "RtlGetCurrentServiceSessionId"
0x14001af55  mov     rcx, rbx; hModule
0x14001af58  call    cs:__imp_GetProcAddress
0x14001af5e  test    rax, rax
0x14001af61  jnz     short loc_14001AF7C
0x14001af63  mov     rcx, cs:WPP_GLOBAL_Control
0x14001af6a  cmp     rcx, r12
0x14001af6d  jz      short loc_14001AF49
0x14001af6f  test    [rcx+1Ch], r15b
0x14001af73  jz      short loc_14001AF49
0x14001af75  mov     edx, 99h
0x14001af7a  jmp     short loc_14001AF32
0x14001af7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af81  test    eax, eax
0x14001af83  setnz   dil
0x14001af87  mov     rcx, cs:WPP_GLOBAL_Control
0x14001af8e  test    rbx, rbx
0x14001af91  jz      short loc_14001AFA3
0x14001af93  mov     rcx, rbx; hLibModule
0x14001af96  call    cs:__imp_FreeLibrary
0x14001af9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001afa3  test    dil, dil
0x14001afa6  jz      short loc_14001AFCF
0x14001afa8  cmp     rcx, r12
0x14001afab  jz      short loc_14001AFC8
0x14001afad  test    byte ptr [rcx+1Ch], 4
0x14001afb1  jz      short loc_14001AFC8
0x14001afb3  mov     edx, 1Ch
0x14001afb8  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001afbf  mov     rcx, [rcx+10h]
0x14001afc3  call    WPP_SF_
0x14001afc8  xor     eax, eax
0x14001afca  jmp     loc_14001B11B
0x14001afcf  xor     edi, edi
0x14001afd1  xor     edx, edx; dwCoInit
0x14001afd3  xor     ecx, ecx; pvReserved
0x14001afd5  call    cs:__imp_CoInitializeEx
0x14001afdb  mov     ebx, eax
0x14001afdd  mov     dword ptr [rbp+arg_8], eax
0x14001afe0  mov     [rbp+arg_10], rdi
0x14001afe4  mov     ecx, 80000000h
0x14001afe9  add     eax, ecx
0x14001afeb  test    ecx, eax
0x14001afed  jnz     short loc_14001B02C
0x14001afef  cmp     ebx, 80010106h
0x14001aff5  jz      short loc_14001B02C
0x14001aff7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001affe  cmp     rcx, r12
0x14001b001  jz      loc_14001B0F9
0x14001b007  test    [rcx+1Ch], r15b
0x14001b00b  jz      loc_14001B0F9
0x14001b011  lea     edx, [rdi+1Dh]
0x14001b014  mov     r9d, ebx
0x14001b017  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001b01e  mov     rcx, [rcx+10h]
0x14001b022  call    WPP_SF_d
0x14001b027  jmp     loc_14001B0F9
0x14001b02c  mov     [rbp+var_28], 0
0x14001b034  lea     rax, [rbp+arg_10]
0x14001b038  mov     [rbp+var_20], rax
0x14001b03c  mov     [rbp+arg_10], 0
0x14001b044  lea     rax, [rbp+var_28]
0x14001b048  mov     [rsp+58h+ppv], rax; ppv
0x14001b04d  lea     r9, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b; riid
0x14001b054  xor     edx, edx; pUnkOuter
0x14001b056  lea     r8d, [rdx+17h]; dwClsContext
0x14001b05a  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x14001b061  call    cs:__imp_CoCreateInstance
0x14001b067  mov     esi, eax
0x14001b069  mov     rax, [rbp+var_28]
0x14001b06d  test    rax, rax
0x14001b070  jz      short loc_14001B08E
0x14001b072  mov     rdx, [rbp+var_20]
0x14001b076  mov     rcx, [rdx]
0x14001b079  mov     [rdx], rax
0x14001b07c  test    rcx, rcx
0x14001b07f  jz      short loc_14001B08E
0x14001b081  mov     rdx, [rcx]
0x14001b084  mov     rax, [rdx+10h]
0x14001b088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b08d  nop
0x14001b08e  test    esi, esi
0x14001b090  jns     short loc_14001B0B1
0x14001b092  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b099  cmp     rcx, r12
0x14001b09c  jz      short loc_14001B0F9
0x14001b09e  test    [rcx+1Ch], r15b
0x14001b0a2  jz      short loc_14001B0F9
0x14001b0a4  mov     edx, 1Eh
0x14001b0a9  mov     r9d, esi
0x14001b0ac  jmp     loc_14001B017
0x14001b0b1  mov     rcx, [rbp+arg_10]
0x14001b0b5  mov     rax, [rcx]
0x14001b0b8  xor     r8d, r8d
0x14001b0bb  lea     rdx, [rbp+arg_0]
0x14001b0bf  mov     rax, [rax+18h]
0x14001b0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b0c8  test    eax, eax
0x14001b0ca  jns     short loc_14001B0EB
0x14001b0cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b0d3  cmp     rcx, r12
0x14001b0d6  jz      short loc_14001B0F9
0x14001b0d8  test    [rcx+1Ch], r15b
0x14001b0dc  jz      short loc_14001B0F9
0x14001b0de  mov     edx, 1Fh
0x14001b0e3  mov     r9d, eax
0x14001b0e6  jmp     loc_14001B017
0x14001b0eb  mov     eax, [rbp+arg_0]
0x14001b0ee  test    eax, eax
0x14001b0f0  jz      short loc_14001B0F9
0x14001b0f2  test    r15b, al
0x14001b0f5  cmovz   edi, r15d
0x14001b0f9  mov     rcx, [rbp+arg_10]
0x14001b0fd  test    rcx, rcx
0x14001b100  jz      short loc_14001B10F
0x14001b102  mov     rax, [rcx]
0x14001b105  mov     rax, [rax+10h]
0x14001b109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b10e  nop
0x14001b10f  test    ebx, ebx
0x14001b111  js      short loc_14001B119
0x14001b113  call    cs:__imp_CoUninitialize
0x14001b119  mov     eax, edi
0x14001b11b  add     rsp, 58h
0x14001b11f  pop     r15
0x14001b121  pop     r12
0x14001b123  pop     rdi
0x14001b124  pop     rsi
0x14001b125  pop     rbx
0x14001b126  pop     rbp
0x14001b127  retn
```
