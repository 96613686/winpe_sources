# p9fs::File::Link(std::basic_string_view<char,std::char_traits<char>>,p9fs::Fid &)

- ea: `0x18001fbb0`
- end: `0x18001fe16`
- name: `?Link@File@p9fs@@UEAAJV?$basic_string_view@DU?$char_traits@D@std@@@std@@AEAVFid@2@@Z`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x180004120`
- `0x180004b00`
- `0x180004c80`
- `0x1800074e0`
- `0x18001d7cc`
- `0x18001d940`
- `0x18001da9c`
- `0x18001e428`
- `0x18001fbb0`
- `0x180020520`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fdbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fdbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall p9fs::File::Link(__int64 a1, __int128 *a2, const struct p9fs::File *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  bool v8; // di
  volatile signed __int32 *v9; // rbx
  __int64 v11; // rax
  const char *v12; // r9
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 *v15; // rcx
  __int64 v16; // rax
  _QWORD *v17; // rdx
  __int128 v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+40h] [rbp-C0h]
  _BYTE v20[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h]
  _BYTE v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v23[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[144]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v19 = 0;
  v6 = *(_QWORD *)a3;
  v18 = 0;
  v7 = *(_QWORD *)(a1 + 80);
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v18 = *(_OWORD *)(a1 + 72);
  v19 = 1;
  v8 = !(*(unsigned __int8 (__fastcall **)(const struct p9fs::File *, __int128 *))(v6 + 216))(a3, &v18)
    || !(*(unsigned __int8 (__fastcall **)(const struct p9fs::File *))(*(_QWORD *)a3 + 224LL))(a3);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v18 + 1);
  if ( *((_QWORD *)&v18 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v18 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  if ( v8 )
    return 4294967274LL;
  v11 = *(_QWORD *)(a1 + 72);
  if ( (*(_BYTE *)(v11 + 48) & 1) != 0 )
    return 4294967266LL;
  if ( *(char *)(v11 + 48) < 0 )
    return 4294967283LL;
  if ( (*(_BYTE *)(v11 + 40) & 0x20) == 0 )
    return 0xFFFFFFFFLL;
  v18 = *a2;
  p9fs::File::ChildPath(a1, v22, &v18);
  if ( !v22[0] )
    return LODWORD(v23[0]);
  memset_0(v24, 0, sizeof(v24));
  _castguard_slow_path_check_fastfail(*(_QWORD *)a3, 248, 0);
  p9fs::File::File((p9fs::File *)v24, a3);
  p9fs::File::OpenHandle(v24, v20, 1048832);
  if ( v20[0] )
  {
    if ( !v22[0] )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\vm\\inc\\expected.h",
        v12);
    v14 = *(_QWORD *)(a1 + 72);
    v15 = *(__int64 **)(v14 + 112);
    v16 = *v15;
    v17 = v23;
    if ( v23[3] > 7u )
      v17 = (_QWORD *)v23[0];
    *(_QWORD *)&v18 = v17;
    *((_QWORD *)&v18 + 1) = v23[2];
    v13 = (*(__int64 (__fastcall **)(__int64 *, HANDLE, _QWORD, __int128 *))(v16 + 40))(
            v15,
            hObject,
            *(_QWORD *)(v14 + 24),
            &v18);
    if ( v20[0] && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  else
  {
    v13 = (unsigned int)hObject;
  }
  p9fs::File::~File((p9fs::File *)v24);
  if ( v22[0] )
    std::wstring::~wstring(v23);
  return v13;
}

```

## disassembly

```asm
0x18001fbb0  mov     [rsp-8+arg_18], rbx
0x18001fbb5  push    rbp
0x18001fbb6  push    rsi
0x18001fbb7  push    rdi
0x18001fbb8  push    r14
0x18001fbba  push    r15
0x18001fbbc  lea     rbp, [rsp-20h]
0x18001fbc1  sub     rsp, 120h
0x18001fbc8  mov     rax, cs:__security_cookie
0x18001fbcf  xor     rax, rsp
0x18001fbd2  mov     [rbp+40h+var_30], rax
0x18001fbd6  mov     rsi, r8
0x18001fbd9  mov     r15, rdx
0x18001fbdc  mov     r14, rcx
0x18001fbdf  mov     [rsp+140h+var_100], 0
0x18001fbe7  mov     rax, [r8]
0x18001fbea  xorps   xmm0, xmm0
0x18001fbed  movdqu  [rsp+140h+var_110], xmm0
0x18001fbf3  mov     rcx, [rcx+50h]
0x18001fbf7  test    rcx, rcx
0x18001fbfa  jz      short loc_18001FC00
0x18001fbfc  lock inc dword ptr [rcx+8]
0x18001fc00  mov     rcx, [r14+48h]
0x18001fc04  mov     qword ptr [rsp+140h+var_110], rcx
0x18001fc09  mov     rcx, [r14+50h]
0x18001fc0d  mov     qword ptr [rsp+140h+var_110+8], rcx
0x18001fc12  mov     [rsp+140h+var_100], 1
0x18001fc1a  lea     rdx, [rsp+140h+var_110]
0x18001fc1f  mov     rcx, rsi
0x18001fc22  mov     rax, [rax+0D8h]
0x18001fc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc2e  test    al, al
0x18001fc30  jz      short loc_18001FC4D
0x18001fc32  mov     rax, [rsi]
0x18001fc35  mov     rcx, rsi
0x18001fc38  mov     rax, [rax+0E0h]
0x18001fc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc44  test    al, al
0x18001fc46  jz      short loc_18001FC4D
0x18001fc48  xor     dil, dil
0x18001fc4b  jmp     short loc_18001FC50
0x18001fc4d  mov     dil, 1
0x18001fc50  mov     rbx, qword ptr [rsp+140h+var_110+8]
0x18001fc55  test    rbx, rbx
0x18001fc58  jz      short loc_18001FC91
0x18001fc5a  or      eax, 0FFFFFFFFh
0x18001fc5d  lock xadd [rbx+8], eax
0x18001fc62  cmp     eax, 1
0x18001fc65  jnz     short loc_18001FC91
0x18001fc67  mov     rax, [rbx]
0x18001fc6a  mov     rcx, rbx
0x18001fc6d  mov     rax, [rax]
0x18001fc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc75  or      eax, 0FFFFFFFFh
0x18001fc78  lock xadd [rbx+0Ch], eax
0x18001fc7d  cmp     eax, 1
0x18001fc80  jnz     short loc_18001FC91
0x18001fc82  mov     rax, [rbx]
0x18001fc85  mov     rcx, rbx
0x18001fc88  mov     rax, [rax+8]
0x18001fc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc91  test    dil, dil
0x18001fc94  jz      short loc_18001FCA0
0x18001fc96  mov     eax, 0FFFFFFEAh
0x18001fc9b  jmp     loc_18001FDE1
0x18001fca0  mov     rax, [r14+48h]
0x18001fca4  test    byte ptr [rax+30h], 1
0x18001fca8  jz      short loc_18001FCB4
0x18001fcaa  mov     eax, 0FFFFFFE2h
0x18001fcaf  jmp     loc_18001FDE1
0x18001fcb4  test    byte ptr [rax+30h], 80h
0x18001fcb8  jz      short loc_18001FCC4
0x18001fcba  mov     eax, 0FFFFFFF3h
0x18001fcbf  jmp     loc_18001FDE1
0x18001fcc4  test    byte ptr [rax+28h], 20h
0x18001fcc8  jnz     short loc_18001FCD2
0x18001fcca  or      eax, 0FFFFFFFFh
0x18001fccd  jmp     loc_18001FDE1
0x18001fcd2  movups  xmm0, xmmword ptr [r15]
0x18001fcd6  movdqu  [rsp+140h+var_110], xmm0
0x18001fcdc  lea     r8, [rsp+140h+var_110]
0x18001fce1  lea     rdx, [rsp+140h+var_E8]
0x18001fce6  mov     rcx, r14
0x18001fce9  call    ?ChildPath@File@p9fs@@QEAA?AV?$BasicExpected@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; p9fs::File::ChildPath(std::string_view)
0x18001fcee  nop
0x18001fcef  cmp     [rsp+140h+var_E8], 0
0x18001fcf4  jnz     short loc_18001FCFF
0x18001fcf6  mov     eax, dword ptr [rsp+140h+var_E0]
0x18001fcfa  jmp     loc_18001FDE1
0x18001fcff  xor     edx, edx; Val
0x18001fd01  mov     r8d, 90h; Size
0x18001fd07  lea     rcx, [rbp+40h+var_C0]; void *
0x18001fd0b  call    memset_0
0x18001fd10  xor     r8d, r8d
0x18001fd13  mov     edx, 0F8h
0x18001fd18  mov     rcx, [rsi]
0x18001fd1b  call    __castguard_slow_path_check_fastfail
0x18001fd20  mov     rdx, rsi; struct p9fs::File *
0x18001fd23  lea     rcx, [rbp+40h+var_C0]; this
0x18001fd27  call    ??0File@p9fs@@QEAA@AEBV01@@Z; p9fs::File::File(p9fs::File const &)
0x18001fd2c  nop
0x18001fd2d  mov     r8d, 100100h
0x18001fd33  lea     rdx, [rsp+140h+var_F8]
0x18001fd38  lea     rcx, [rbp+40h+var_C0]
0x18001fd3c  call    ?OpenHandle@File@p9fs@@AEBA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@K@Z; p9fs::File::OpenHandle(ulong)
0x18001fd41  nop
0x18001fd42  cmp     [rsp+140h+var_F8], 0
0x18001fd47  jnz     short loc_18001FD4F
0x18001fd49  mov     ebx, dword ptr [rsp+140h+hObject]
0x18001fd4d  jmp     short loc_18001FDC4
0x18001fd4f  cmp     [rsp+140h+var_E8], 0
0x18001fd54  setz    al
0x18001fd57  mov     rcx, [rbp+48h]; this
0x18001fd5b  test    al, al
0x18001fd5d  jnz     loc_18001FE04
0x18001fd63  mov     r8, [r14+48h]
0x18001fd67  mov     rcx, [r8+70h]
0x18001fd6b  mov     rax, [rcx]
0x18001fd6e  lea     rdx, [rsp+140h+var_E0]
0x18001fd73  cmp     [rsp+140h+var_C8], 7
0x18001fd79  cmova   rdx, [rsp+140h+var_E0]
0x18001fd7f  mov     qword ptr [rsp+140h+var_110], rdx
0x18001fd84  mov     rdx, [rsp+140h+var_D0]
0x18001fd89  mov     qword ptr [rsp+140h+var_110+8], rdx
0x18001fd8e  lea     r9, [rsp+140h+var_110]
0x18001fd93  mov     r8, [r8+18h]
0x18001fd97  mov     rdx, [rsp+140h+hObject]
0x18001fd9c  mov     rax, [rax+28h]
0x18001fda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fda5  mov     ebx, eax
0x18001fda7  cmp     [rsp+140h+var_F8], 0
0x18001fdac  jz      short loc_18001FDC4
0x18001fdae  mov     rcx, [rsp+140h+hObject]; hObject
0x18001fdb3  lea     rdx, [rcx-1]
0x18001fdb7  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001fdbb  ja      short loc_18001FDC4
0x18001fdbd  call    cs:__imp_CloseHandle
0x18001fdc3  nop
0x18001fdc4  lea     rcx, [rbp+40h+var_C0]; this
0x18001fdc8  call    ??1File@p9fs@@UEAA@XZ; p9fs::File::~File(void)
0x18001fdcd  nop
0x18001fdce  cmp     [rsp+140h+var_E8], 0
0x18001fdd3  jz      short loc_18001FDDF
0x18001fdd5  lea     rcx, [rsp+140h+var_E0]
0x18001fdda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fddf  mov     eax, ebx
0x18001fde1  mov     rcx, [rbp+40h+var_30]
0x18001fde5  xor     rcx, rsp; StackCookie
0x18001fde8  call    __security_check_cookie
0x18001fded  mov     rbx, [rsp+140h+arg_18]
0x18001fdf5  add     rsp, 120h
0x18001fdfc  pop     r15
0x18001fdfe  pop     r14
0x18001fe00  pop     rdi
0x18001fe01  pop     rsi
0x18001fe02  pop     rbp
0x18001fe03  retn
0x18001fe04  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x18001fe0b  mov     edx, 139h; void *
0x18001fe10  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
