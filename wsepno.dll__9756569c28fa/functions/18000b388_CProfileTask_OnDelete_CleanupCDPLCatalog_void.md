# CProfileTask_OnDelete::_CleanupCDPLCatalog(void)

- ea: `0x18000b388`
- end: `0x18000b48c`
- name: `?_CleanupCDPLCatalog@CProfileTask_OnDelete@@AEAAJXZ`
- size: `260`
- prototype: `__int64 __fastcall(CProfileTask_OnDelete *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006b50`

## callees

- `0x18000a374`
- `0x18000b388`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b3bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b3bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CProfileTask_OnDelete::_CleanupCDPLCatalog(CProfileTask_OnDelete *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v4; // rcx
  int v6; // eax
  LPVOID v7; // rcx
  LPVOID v8; // rcx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = 0;
  v2 = CoCreateInstance(
         &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
         0,
         0x15u,
         &GUID_dbab3f73_db19_4a79_bfc0_a61a93886ddf,
         &v11);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\profnotif\\profnotif.cpp",
      (const char *)(unsigned int)v2,
      v9);
    v4 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return v3;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v11 + 136LL))(v11, *((_QWORD *)this + 2));
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\profnotif\\profnotif.cpp",
      (const char *)(unsigned int)v6,
      v9);
    v7 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v3;
  }
  v8 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b388  mov     r11, rsp
0x18000b38b  mov     [r11+8], rbx
0x18000b38f  push    rdi
0x18000b390  sub     rsp, 30h
0x18000b394  mov     rdi, rcx
0x18000b397  mov     qword ptr [r11+10h], 0
0x18000b39f  lea     rax, [r11+10h]
0x18000b3a3  mov     [r11-18h], rax
0x18000b3a7  lea     r9, _GUID_dbab3f73_db19_4a79_bfc0_a61a93886ddf; riid
0x18000b3ae  xor     edx, edx; pUnkOuter
0x18000b3b0  lea     r8d, [rdx+15h]; dwClsContext
0x18000b3b4  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x18000b3bb  call    cs:__imp_CoCreateInstance
0x18000b3c1  mov     ebx, eax
0x18000b3c3  test    eax, eax
0x18000b3c5  jns     short loc_18000B405
0x18000b3c7  mov     rcx, [rsp+38h]; this
0x18000b3cc  mov     r9d, eax; char *
0x18000b3cf  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18000b3d6  mov     edx, 2A0h; void *
0x18000b3db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3e0  nop
0x18000b3e1  mov     rcx, [rsp+38h+arg_8]
0x18000b3e6  test    rcx, rcx
0x18000b3e9  jz      short loc_18000B401
0x18000b3eb  mov     [rsp+38h+arg_8], 0
0x18000b3f4  mov     rax, [rcx]
0x18000b3f7  mov     rax, [rax+10h]
0x18000b3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b400  nop
0x18000b401  mov     eax, ebx
0x18000b403  jmp     short loc_18000B481
0x18000b405  mov     rcx, [rsp+38h+arg_8]
0x18000b40a  mov     rax, [rcx]
0x18000b40d  mov     rdx, [rdi+10h]
0x18000b411  mov     rax, [rax+88h]
0x18000b418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b41d  mov     ebx, eax
0x18000b41f  test    eax, eax
0x18000b421  jns     short loc_18000B45F
0x18000b423  mov     rcx, [rsp+38h]; this
0x18000b428  mov     r9d, eax; char *
0x18000b42b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18000b432  mov     edx, 2A2h; void *
0x18000b437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b43c  nop
0x18000b43d  mov     rcx, [rsp+38h+arg_8]
0x18000b442  test    rcx, rcx
0x18000b445  jz      short loc_18000B45D
0x18000b447  mov     [rsp+38h+arg_8], 0
0x18000b450  mov     rax, [rcx]
0x18000b453  mov     rax, [rax+10h]
0x18000b457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b45c  nop
0x18000b45d  jmp     short loc_18000B401
0x18000b45f  mov     rcx, [rsp+38h+arg_8]
0x18000b464  test    rcx, rcx
0x18000b467  jz      short loc_18000B47F
0x18000b469  mov     [rsp+38h+arg_8], 0
0x18000b472  mov     rax, [rcx]
0x18000b475  mov     rax, [rax+10h]
0x18000b479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b47e  nop
0x18000b47f  xor     eax, eax
0x18000b481  mov     rbx, [rsp+38h+arg_0]
0x18000b486  add     rsp, 30h
0x18000b48a  pop     rdi
0x18000b48b  retn
```
