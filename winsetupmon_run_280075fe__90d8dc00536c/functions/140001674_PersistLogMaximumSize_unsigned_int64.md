# PersistLogMaximumSize(unsigned __int64)

- ea: `0x140001674`
- end: `0x140001740`
- name: `?PersistLogMaximumSize@@YAJ_K@Z`
- size: `204`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140002f00`

## callees

- `0x140001674`
- `0x1400018a8`
- `0x140001a10`
- `0x140003944`
- `0x14000a680`
- `0x14000f9e0`

## string_xrefs

- `0x1400016e8`: `Failed to create updated log configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall PersistLogMaximumSize(__int64 a1)
{
  int v2; // eax
  __int64 (__fastcall ***v3)(_QWORD); // rbx
  unsigned int v4; // edi
  _QWORD *v5; // rax
  int v6; // eax
  struct IWsmLogConfig *v7; // rsi
  _QWORD v9[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 (__fastcall ***v10)(_QWORD); // [rsp+48h] [rbp+10h] BYREF
  struct IWsmLogConfig *v11; // [rsp+50h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  v2 = QueryLogConfig(&v10);
  v3 = v10;
  v4 = v2;
  if ( v2 >= 0 )
  {
    if ( !v10 )
      return v4;
    v5 = (_QWORD *)(**v10)(v10);
    v9[1] = a1;
    v9[0] = *v5;
    v6 = CreateInstance((struct _WSM_LOG_CONFIG *const)v9, &v11);
    v7 = v11;
    v4 = v6;
    if ( v6 >= 0 )
      v4 = SetLogConfig((__int64)v11);
    else
      WriteLogMessage(3, L"Failed to create updated log configuration (0x%08X)", (unsigned int)v6);
    if ( v7 )
      (*(void (__fastcall **)(struct IWsmLogConfig *))(*(_QWORD *)v7 + 8LL))(v7);
  }
  if ( v3 )
    (*v3)[1](v3);
  return v4;
}

```

## disassembly

```asm
0x140001674  mov     rax, rsp
0x140001677  mov     [rax+8], rbx
0x14000167b  mov     [rax+20h], rsi
0x14000167f  push    rdi
0x140001680  sub     rsp, 30h
0x140001684  mov     rsi, rcx
0x140001687  mov     qword ptr [rax+10h], 0
0x14000168f  lea     rcx, [rax+10h]
0x140001693  mov     qword ptr [rax+18h], 0
0x14000169b  call    QueryLogConfig
0x1400016a0  mov     rbx, [rsp+38h+arg_8]
0x1400016a5  mov     edi, eax
0x1400016a7  test    eax, eax
0x1400016a9  js      short loc_140001719
0x1400016ab  test    rbx, rbx
0x1400016ae  jz      short loc_14000172D
0x1400016b0  mov     rax, [rbx]
0x1400016b3  mov     rcx, rbx
0x1400016b6  mov     rax, [rax]
0x1400016b9  call    _guard_dispatch_icall
0x1400016be  lea     rdx, [rsp+38h+arg_10]; struct IWsmLogConfig **
0x1400016c3  mov     [rsp+38h+var_10], rsi
0x1400016c8  mov     rcx, [rax]
0x1400016cb  mov     [rsp+38h+var_18], rcx
0x1400016d0  lea     rcx, [rsp+38h+var_18]; struct _WSM_LOG_CONFIG *
0x1400016d5  call    ?CreateInstance@@YAJQEAU_WSM_LOG_CONFIG@@PEAPEAVIWsmLogConfig@@@Z; CreateInstance(_WSM_LOG_CONFIG * const,IWsmLogConfig * *)
0x1400016da  mov     rsi, [rsp+38h+arg_10]
0x1400016df  mov     edi, eax
0x1400016e1  test    eax, eax
0x1400016e3  jns     short loc_1400016FB
0x1400016e5  mov     r8d, eax
0x1400016e8  lea     rdx, aFailedToCreate; "Failed to create updated log configurat"...
0x1400016ef  mov     ecx, 3
0x1400016f4  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400016f9  jmp     short loc_140001705
0x1400016fb  mov     rcx, rsi
0x1400016fe  call    SetLogConfig
0x140001703  mov     edi, eax
0x140001705  test    rsi, rsi
0x140001708  jz      short loc_140001719
0x14000170a  mov     rax, [rsi]
0x14000170d  mov     rcx, rsi
0x140001710  mov     rax, [rax+8]
0x140001714  call    _guard_dispatch_icall
0x140001719  test    rbx, rbx
0x14000171c  jz      short loc_14000172D
0x14000171e  mov     rax, [rbx]
0x140001721  mov     rcx, rbx
0x140001724  mov     rax, [rax+8]
0x140001728  call    _guard_dispatch_icall
0x14000172d  mov     rbx, [rsp+38h+arg_0]
0x140001732  mov     eax, edi
0x140001734  mov     rsi, [rsp+38h+arg_18]
0x140001739  add     rsp, 30h
0x14000173d  pop     rdi
0x14000173e  retn
```
