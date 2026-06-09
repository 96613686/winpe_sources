# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18000dbe8`
- end: `0x18000ddbc`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `468`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d880`
- `0x18000d900`

## callees

- `0x180005e00`
- `0x1800061f0`
- `0x18000dbe8`
- `0x18008fe00`
- `0x180096170`
- `0x1800961f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dd7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dcea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dd01`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dd01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000dd8d`

## string_xrefs

- `0x18000dce3`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  __int64 v4; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // ecx
  __int128 v8; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+48h] [rbp-C0h]
  __int128 v10; // [rsp+58h] [rbp-B0h]
  LPVOID pv; // [rsp+68h] [rbp-A0h] BYREF
  char v12; // [rsp+70h] [rbp-98h]
  int v13; // [rsp+71h] [rbp-97h] BYREF
  char v14; // [rsp+75h] [rbp-93h]
  _BYTE v15[2050]; // [rsp+76h] [rbp-92h] BYREF
  int *v16; // [rsp+878h] [rbp+770h]
  _BYTE *v17; // [rsp+880h] [rbp+778h]
  _BYTE *v18; // [rsp+888h] [rbp+780h]

  v2 = *(_DWORD *)(a1 + 64) | 0x800;
  *(_DWORD *)(a1 + 64) = v2;
  if ( *(_QWORD *)(a1 + 240) && (v2 & 0x100) == 0 && *(_DWORD *)(a1 + 232) == 1 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    memset(v15, 0, sizeof(v15));
    pv = 0;
    v12 = 0;
    v16 = &v13;
    v18 = &v15[2043];
    v13 = -2143256512;
    v14 = 0;
    v17 = v15;
    v3 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, 1);
    v4 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_9;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_9:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v4, 0, v3, &v8);
    }
    else
    {
      v8 = 0;
      v9 = 0;
      v10 = 0;
    }
    v7 = v9;
    *(_DWORD *)(a1 + 64) |= DWORD1(v9);
    if ( *((_QWORD *)&v9 + 1) )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v8);
    else
      *(_DWORD *)(a1 + 184) = v7;
    if ( pv )
      CoTaskMemFree(pv);
    CoTaskMemFree(*((LPVOID *)&v9 + 1));
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18000dbe8  mov     rax, rsp
0x18000dbeb  mov     [rax+10h], rbx
0x18000dbef  mov     [rax+18h], rsi
0x18000dbf3  mov     [rax+20h], rdi
0x18000dbf7  push    rbp
0x18000dbf8  lea     rbp, [rax-7A8h]
0x18000dbff  sub     rsp, 8A0h
0x18000dc06  mov     rax, cs:__security_cookie
0x18000dc0d  xor     rax, rsp
0x18000dc10  mov     [rbp+7A0h+var_10], rax
0x18000dc17  mov     rbx, rcx
0x18000dc1a  mov     eax, [rcx+40h]
0x18000dc1d  bts     eax, 0Bh
0x18000dc21  mov     [rcx+40h], eax
0x18000dc24  cmp     qword ptr [rcx+0F0h], 0
0x18000dc2c  jz      loc_18000DD80
0x18000dc32  bt      eax, 8
0x18000dc36  jb      loc_18000DD80
0x18000dc3c  cmp     dword ptr [rcx+0E8h], 1
0x18000dc43  jnz     loc_18000DD80
0x18000dc49  xorps   xmm0, xmm0
0x18000dc4c  movups  [rsp+8A0h+var_878+8], xmm0
0x18000dc51  movups  [rsp+8A0h+var_868+8], xmm0
0x18000dc56  movups  xmmword ptr [rsp+8A0h+var_858+8], xmm0
0x18000dc5b  xor     edx, edx; Val
0x18000dc5d  mov     r8d, 802h; Size
0x18000dc63  lea     rcx, [rsp+8A0h+var_832]; void *
0x18000dc68  call    memset
0x18000dc6d  mov     [rsp+8A0h+pv], 0
0x18000dc76  mov     [rsp+8A0h+var_838], 0
0x18000dc7b  lea     rax, [rsp+8A0h+var_837]
0x18000dc80  mov     [rbp+7A0h+var_30], rax
0x18000dc87  lea     rax, [rbp+7A0h+var_37]
0x18000dc8e  mov     [rbp+7A0h+var_20], rax
0x18000dc95  mov     [rsp+8A0h+var_837], 80408040h
0x18000dc9d  mov     [rsp+8A0h+var_833], 0
0x18000dca2  lea     rax, [rsp+8A0h+var_832]
0x18000dca7  mov     [rbp+7A0h+var_28], rax
0x18000dcae  mov     r8d, 1
0x18000dcb4  lea     rdx, [rsp+8A0h+pv]
0x18000dcb9  mov     rcx, rbx
0x18000dcbc  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000dcc1  mov     rdi, rax
0x18000dcc4  mov     rsi, [rbx+0F0h]
0x18000dccb  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18000dcd2  test    rax, rax
0x18000dcd5  jnz     short loc_18000DD27
0x18000dcd7  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000dcde  test    rax, rax
0x18000dce1  jnz     short loc_18000DCF7
0x18000dce3  lea     rcx, ModuleName; "kernelbase.dll"
0x18000dcea  call    cs:__imp_GetModuleHandleW
0x18000dcf0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000dcf7  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18000dcfe  mov     rcx, rax; hModule
0x18000dd01  call    cs:__imp_GetProcAddress
0x18000dd07  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18000dd0e  test    rax, rax
0x18000dd11  jnz     short loc_18000DD27
0x18000dd13  xorps   xmm0, xmm0
0x18000dd16  movups  [rsp+8A0h+var_878+8], xmm0
0x18000dd1b  movups  [rsp+8A0h+var_868+8], xmm0
0x18000dd20  movups  xmmword ptr [rsp+8A0h+var_858+8], xmm0
0x18000dd25  jmp     short loc_18000DD39
0x18000dd27  lea     r9, [rsp+8A0h+var_878+8]
0x18000dd2c  mov     r8, rdi
0x18000dd2f  xor     edx, edx
0x18000dd31  mov     rcx, rsi
0x18000dd34  call    _guard_dispatch_icall
0x18000dd39  mov     rcx, qword ptr [rsp+8A0h+var_868+8]
0x18000dd3e  mov     rax, rcx
0x18000dd41  shr     rax, 20h
0x18000dd45  or      [rbx+40h], eax
0x18000dd48  cmp     qword ptr [rsp+8A0h+var_858], 0
0x18000dd4e  jz      short loc_18000DD5F
0x18000dd50  lea     rdx, [rsp+8A0h+var_878+8]
0x18000dd55  mov     rcx, rbx
0x18000dd58  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18000dd5d  jmp     short loc_18000DD65
0x18000dd5f  mov     [rbx+0B8h], ecx
0x18000dd65  mov     rcx, [rsp+8A0h+pv]; pv
0x18000dd6a  test    rcx, rcx
0x18000dd6d  jz      short loc_18000DD75
0x18000dd6f  call    cs:__imp_CoTaskMemFree
0x18000dd75  mov     rcx, qword ptr [rsp+8A0h+var_858]; pv
0x18000dd7a  call    cs:__imp_CoTaskMemFree
0x18000dd80  dec     dword ptr [rbx+0E8h]
0x18000dd86  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000dd8d  call    cs:__imp_LeaveCriticalSection
0x18000dd93  nop
0x18000dd94  mov     rcx, [rbp+7A0h+var_10]
0x18000dd9b  xor     rcx, rsp; StackCookie
0x18000dd9e  call    __security_check_cookie
0x18000dda3  lea     r11, [rsp+8A0h+var_s0]
0x18000ddab  mov     rbx, [r11+18h]
0x18000ddaf  mov     rsi, [r11+20h]
0x18000ddb3  mov     rdi, [r11+28h]
0x18000ddb7  mov     rsp, r11
0x18000ddba  pop     rbp
0x18000ddbb  retn
```
