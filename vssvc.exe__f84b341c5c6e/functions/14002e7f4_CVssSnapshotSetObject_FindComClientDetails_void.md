# CVssSnapshotSetObject::FindComClientDetails(void)

- ea: `0x14002e7f4`
- end: `0x14002eb16`
- name: `?FindComClientDetails@CVssSnapshotSetObject@@QEAAJXZ`
- size: `802`
- prototype: `__int64 __fastcall(CVssSnapshotSetObject *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140085f00`
- `0x140099aa0`
- `0x14009aa00`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14002e7f4`
- `0x14002f438`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002e8b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002e8b0`
- `VssTrace!__imp_VssTraceMessage` at `0x14002e9ce`
- `VssTrace!__imp_VssTraceMessage` at `0x14002e9ce`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002e91d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002e91d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002e90e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002e90e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14002ea17`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14002ea17`

## string_xrefs

- `0x14002e814`: `CVssSnapshotSetObject::FindComClientDetails`
- `0x14002ea4f`: `CVssSnapshotSetObject::FindComClientDetails`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssSnapshotSetObject::FindComClientDetails(CVssSnapshotSetObject *this)
{
  int v2; // eax
  __int64 v3; // rcx
  int v4; // ebx
  DWORD v5; // ecx
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // ebx
  bool v8; // sf
  unsigned int v9; // edi
  unsigned int v10; // esi
  __int16 v11; // ax
  unsigned int v12; // ebx
  __int64 v14; // [rsp+20h] [rbp-188h]
  __int64 v15; // [rsp+28h] [rbp-180h]
  unsigned __int64 v16; // [rsp+50h] [rbp-158h] BYREF
  unsigned int v17; // [rsp+58h] [rbp-150h]
  const unsigned __int16 *v18; // [rsp+60h] [rbp-148h]
  const unsigned __int16 *v19; // [rsp+68h] [rbp-140h]
  unsigned int v20; // [rsp+70h] [rbp-138h]
  unsigned int v21; // [rsp+74h] [rbp-134h]
  const unsigned __int16 *v22; // [rsp+78h] [rbp-130h]
  unsigned int v23; // [rsp+80h] [rbp-128h]
  DWORD TickCount; // [rsp+84h] [rbp-124h]
  int v25; // [rsp+88h] [rbp-120h]
  __int128 v26; // [rsp+90h] [rbp-118h]
  __int128 v27; // [rsp+A0h] [rbp-108h]
  __int64 v28; // [rsp+B0h] [rbp-F8h]
  int v29; // [rsp+C0h] [rbp-E8h] BYREF
  const unsigned __int16 *v30; // [rsp+C8h] [rbp-E0h] BYREF
  const unsigned __int16 *v31; // [rsp+D0h] [rbp-D8h]
  const unsigned __int16 *v32; // [rsp+D8h] [rbp-D0h]
  int v33; // [rsp+E0h] [rbp-C8h]
  int v34; // [rsp+E4h] [rbp-C4h]
  int v35; // [rsp+E8h] [rbp-C0h]
  _BYTE v36[120]; // [rsp+F0h] [rbp-B8h] BYREF
  int v37; // [rsp+168h] [rbp-40h]
  _com_error *v38; // [rsp+170h] [rbp-38h] BYREF
  const std::exception *v39; // [rsp+178h] [rbp-30h] BYREF
  __int64 v40; // [rsp+1B0h] [rbp+8h] BYREF

  v30 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v31 = L"CVssSnapshotSetObject::FindComClientDetails";
  v32 = L"CORSNPSC";
  v33 = 2357;
  v34 = 1;
  v35 = 255;
  v37 = 0x1000000;
  memset_0(v36, 0, sizeof(v36));
  v17 = 0;
  v22 = L"CVssSnapshotSetObject::FindComClientDetails";
  v18 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
  v19 = L"CORSNPSC";
  v20 = 2357;
  v21 = 1;
  TickCount = GetTickCount();
  v25 = 255;
  v16 = 0xFFFFFFFF00000000uLL;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  v40 = 0;
  if ( (int)VssGetTracingContextPerThread(&v40) < 0 )
  {
    v3 = v28;
  }
  else
  {
    v2 = VssSetTracingContextPerThread(&v16);
    v3 = v28;
    if ( v2 >= 0 )
      v3 = v40;
    v28 = v3;
  }
  if ( v3 )
    v23 = *(_DWORD *)(v3 + 48) + 1;
  else
    v23 = 0;
  v4 = 160;
  if ( v25 != 255 )
    v4 = v25;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v16) )
    VssTraceMessage(v18, v19, v20, v23, v21, v22, L"ENTER", v4, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v30);
  if ( *((_QWORD *)this + 316) || *((_DWORD *)this + 634) )
  {
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v16);
    return 1;
  }
  else
  {
    try
    {
      *((_QWORD *)this + 316) = GetClientTokenUser(v5);
      *((_DWORD *)this + 634) = 0;
      v6 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)this + 634);
      v7 = v6;
      v8 = v6 < 0;
      if ( v6 > 0 )
        v8 = 1;
      if ( v8 )
      {
        if ( v6 > 0 )
        {
          v9 = (unsigned __int16)v6 | 0x80070000;
          v10 = v9;
        }
        else
        {
          v9 = v6;
          v10 = v6;
        }
        v30 = L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx";
        v31 = L"CVssSnapshotSetObject::FindComClientDetails";
        v32 = L"CORSNPSC";
        v33 = 2373;
        v34 = 1;
        v35 = 255;
        v37 = 0x1000000;
        memset_0(v36, 0, sizeof(v36));
        v11 = 15;
        do
          --v11;
        while ( v11 );
        LODWORD(v15) = v10;
        LODWORD(v14) = v7;
        CVssFunctionTracer::Throw(&v16, &v30, v9, L"Fail to find client PID winerr %d HRESULT 0x%08lx", v14, v15);
      }
    }
    catch ( long v29 )
    {
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)&v16,
        v29,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::FindComClientDetails",
        0x947u,
        v21);
    }
    catch ( _com_error *v38 )
    {
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)&v16,
        v38,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::FindComClientDetails",
        0x947u,
        v21);
    }
    catch ( std::bad_alloc )
    {
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)&v16,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::FindComClientDetails",
        0x947u,
        v21);
    }
    catch ( const std::exception *v39 )
    {
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)&v16,
        v39,
        L"base\\stor\\vss\\modules\\coord\\src\\snap_set.cxx",
        L"CORSNPSC",
        L"CVssSnapshotSetObject::FindComClientDetails",
        0x947u,
        v21);
    }
    v12 = v17;
    CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v16);
    return v12;
  }
}

```

## disassembly

```asm
0x14002e7f4  mov     r11, rsp
0x14002e7f7  push    rbx
0x14002e7f8  push    rsi
0x14002e7f9  push    rdi
0x14002e7fa  push    r13
0x14002e7fc  sub     rsp, 188h
0x14002e803  mov     rdi, rcx
0x14002e806  lea     r13, aBaseStorVssMod; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14002e80d  mov     [r11-0E0h], r13
0x14002e814  lea     rax, aCvsssnapshotse_3; "CVssSnapshotSetObject::FindComClientDet"...
0x14002e81b  mov     [r11-0D8h], rax
0x14002e822  lea     rax, aCorsnpsc; "CORSNPSC"
0x14002e829  mov     [r11-0D0h], rax
0x14002e830  mov     [rsp+1A8h+var_C8], 935h
0x14002e83b  mov     [rsp+1A8h+var_C4], 1
0x14002e846  mov     [rsp+1A8h+var_C0], 0FFh
0x14002e851  mov     dword ptr [r11-40h], 1000000h
0x14002e859  xor     edx, edx; Val
0x14002e85b  lea     r8d, [rdx+78h]; Size
0x14002e85f  lea     rcx, [r11-0B8h]; void *
0x14002e866  call    memset_0
0x14002e86b  mov     [rsp+1A8h+var_150], 0
0x14002e873  mov     rax, [rsp+1A8h+var_D8]
0x14002e87b  mov     [rsp+1A8h+var_130], rax
0x14002e880  mov     rax, [rsp+1A8h+var_E0]
0x14002e888  mov     [rsp+1A8h+var_148], rax
0x14002e88d  mov     rax, [rsp+1A8h+var_D0]
0x14002e895  mov     [rsp+1A8h+var_140], rax
0x14002e89a  mov     eax, [rsp+1A8h+var_C8]
0x14002e8a1  mov     [rsp+1A8h+var_138], eax
0x14002e8a5  mov     eax, [rsp+1A8h+var_C4]
0x14002e8ac  mov     [rsp+1A8h+var_134], eax
0x14002e8b0  call    cs:__imp_GetTickCount
0x14002e8b6  mov     [rsp+1A8h+var_124], eax
0x14002e8bd  mov     [rsp+1A8h+var_154], 0FFFFFFFFh
0x14002e8c5  mov     eax, [rsp+1A8h+var_C0]
0x14002e8cc  mov     [rsp+1A8h+var_120], eax
0x14002e8d3  mov     [rsp+1A8h+var_158], 0
0x14002e8db  mov     [rsp+1A8h+var_F8], 0
0x14002e8e7  xorps   xmm0, xmm0
0x14002e8ea  movups  [rsp+1A8h+var_118], xmm0
0x14002e8f2  movups  [rsp+1A8h+var_108], xmm0
0x14002e8fa  mov     [rsp+1A8h+arg_0], 0
0x14002e906  lea     rcx, [rsp+1A8h+arg_0]
0x14002e90e  call    cs:__imp_VssGetTracingContextPerThread
0x14002e914  test    eax, eax
0x14002e916  js      short loc_14002E940
0x14002e918  lea     rcx, [rsp+1A8h+var_158]
0x14002e91d  call    cs:__imp_VssSetTracingContextPerThread
0x14002e923  mov     rcx, [rsp+1A8h+var_F8]
0x14002e92b  test    eax, eax
0x14002e92d  cmovns  rcx, [rsp+1A8h+arg_0]
0x14002e936  mov     [rsp+1A8h+var_F8], rcx
0x14002e93e  jmp     short loc_14002E948
0x14002e940  mov     rcx, [rsp+1A8h+var_F8]
0x14002e948  test    rcx, rcx
0x14002e94b  jz      short loc_14002E95B
0x14002e94d  mov     eax, [rcx+30h]
0x14002e950  inc     eax
0x14002e952  mov     [rsp+1A8h+var_128], eax
0x14002e959  jmp     short loc_14002E966
0x14002e95b  mov     [rsp+1A8h+var_128], 0
0x14002e966  mov     ebx, 0A0h
0x14002e96b  cmp     [rsp+1A8h+var_120], 0FFh
0x14002e976  cmovnz  ebx, [rsp+1A8h+var_120]
0x14002e97e  lea     rcx, [rsp+1A8h+var_158]; this
0x14002e983  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14002e988  test    eax, eax
0x14002e98a  jz      short loc_14002E9D4
0x14002e98c  mov     [rsp+1A8h+var_168], 0
0x14002e995  mov     [rsp+1A8h+var_170], ebx
0x14002e999  lea     rax, aEnter; "ENTER"
0x14002e9a0  mov     [rsp+1A8h+var_178], rax
0x14002e9a5  mov     rax, [rsp+1A8h+var_130]
0x14002e9aa  mov     [rsp+1A8h+var_180], rax
0x14002e9af  mov     eax, [rsp+1A8h+var_134]
0x14002e9b3  mov     dword ptr [rsp+1A8h+var_188], eax
0x14002e9b7  mov     r9d, [rsp+1A8h+var_128]
0x14002e9bf  mov     r8d, [rsp+1A8h+var_138]
0x14002e9c4  mov     rdx, [rsp+1A8h+var_140]
0x14002e9c9  mov     rcx, [rsp+1A8h+var_148]
0x14002e9ce  call    cs:__imp_VssTraceMessage
0x14002e9d4  lea     rcx, [rsp+1A8h+var_E0]; this
0x14002e9dc  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002e9e1  nop
0x14002e9e2  cmp     qword ptr [rdi+9E0h], 0
0x14002e9ea  jnz     loc_14002EAFA
0x14002e9f0  lea     rbx, [rdi+9E8h]
0x14002e9f7  cmp     dword ptr [rbx], 0
0x14002e9fa  jnz     loc_14002EAFA
0x14002ea00  call    ?GetClientTokenUser@@YAPEAU_TOKEN_USER@@H@Z; GetClientTokenUser(int)
0x14002ea05  mov     [rdi+9E0h], rax
0x14002ea0c  mov     dword ptr [rbx], 0
0x14002ea12  mov     rdx, rbx; Pid
0x14002ea15  xor     ecx, ecx; Binding
0x14002ea17  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14002ea1d  mov     ebx, eax
0x14002ea1f  movzx   edi, ax
0x14002ea22  test    eax, eax
0x14002ea24  jle     short loc_14002EA2F
0x14002ea26  mov     eax, edi
0x14002ea28  or      eax, 80070000h
0x14002ea2d  test    eax, eax
0x14002ea2f  jns     loc_14002EAE0
0x14002ea35  test    ebx, ebx
0x14002ea37  jg      short loc_14002EA3F
0x14002ea39  mov     edi, ebx
0x14002ea3b  mov     esi, ebx
0x14002ea3d  jmp     short loc_14002EA47
0x14002ea3f  or      edi, 80070000h
0x14002ea45  mov     esi, edi
0x14002ea47  mov     [rsp+1A8h+var_E0], r13
0x14002ea4f  lea     rax, aCvsssnapshotse_3; "CVssSnapshotSetObject::FindComClientDet"...
0x14002ea56  mov     [rsp+1A8h+var_D8], rax
0x14002ea5e  lea     rax, aCorsnpsc; "CORSNPSC"
0x14002ea65  mov     [rsp+1A8h+var_D0], rax
0x14002ea6d  mov     [rsp+1A8h+var_C8], 945h
0x14002ea78  mov     [rsp+1A8h+var_C4], 1
0x14002ea83  mov     [rsp+1A8h+var_C0], 0FFh
0x14002ea8e  mov     [rsp+1A8h+var_40], 1000000h
0x14002ea99  xor     edx, edx; Val
0x14002ea9b  lea     r8d, [rdx+78h]; Size
0x14002ea9f  lea     rcx, [rsp+1A8h+var_B8]; void *
0x14002eaa7  call    memset_0
0x14002eaac  mov     eax, 0Fh
0x14002eab1  mov     ecx, 0FFFFh
0x14002eab6  add     ax, cx
0x14002eab9  jnz     short loc_14002EAB1
0x14002eabb  mov     dword ptr [rsp+1A8h+var_180], esi
0x14002eabf  mov     dword ptr [rsp+1A8h+var_188], ebx
0x14002eac3  lea     r9, aFailToFindClie; "Fail to find client PID winerr %d HRESU"...
0x14002eaca  mov     r8d, edi
0x14002eacd  lea     rdx, [rsp+1A8h+var_E0]
0x14002ead5  lea     rcx, [rsp+1A8h+var_158]
0x14002eada  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002eae0  jmp     short loc_14002EAE8
0x14002eae2  jmp     short loc_14002EAE8
0x14002eae4  jmp     short loc_14002EAE8
0x14002eae6  jmp     short $+2
0x14002eae8  mov     ebx, [rsp+1A8h+var_150]
0x14002eaec  lea     rcx, [rsp+1A8h+var_158]; this
0x14002eaf1  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002eaf6  mov     eax, ebx
0x14002eaf8  jmp     short loc_14002EB09
0x14002eafa  lea     rcx, [rsp+1A8h+var_158]; this
0x14002eaff  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002eb04  mov     eax, 1
0x14002eb09  add     rsp, 188h
0x14002eb10  pop     r13
0x14002eb12  pop     rdi
0x14002eb13  pop     rsi
0x14002eb14  pop     rbx
0x14002eb15  retn
```
