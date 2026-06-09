# ATL::CComModule::RegisterClassObjects(ulong,ulong)

- ea: `0x18000be4c`
- end: `0x18000bfb5`
- name: `?RegisterClassObjects@CComModule@ATL@@QEAAJKK@Z`
- size: `361`
- prototype: `__int64 __fastcall(IUnknown *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac34`

## callees

- `0x18000be4c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000becb`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000bf71`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000becb`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x18000bf71`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::RegisterClassObjects(IUnknown *this)
{
  __int64 v1; // rdi
  HRESULT v2; // ebx
  __int64 (__fastcall *v3)(_QWORD, GUID *, LPUNKNOWN *); // rax
  __int64 *v4; // rdi
  __int64 *v5; // rax
  __int64 v6; // rsi
  bool v7; // zf
  LPUNKNOWN pUnk; // [rsp+40h] [rbp+8h] BYREF

  pUnk = this;
  v1 = qword_18002E1D8;
  if ( qword_18002E1D8 && (v2 = 0, *(_QWORD *)qword_18002E1D8) )
  {
    while ( !v2 )
    {
      v3 = *(__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))(v1 + 16);
      pUnk = 0;
      if ( v3 )
      {
        v2 = v3(*(_QWORD *)(v1 + 24), &GUID_00000000_0000_0000_c000_000000000046, &pUnk);
        if ( v2 >= 0 )
          v2 = CoRegisterClassObject(*(const IID *const *)v1, pUnk, 4u, 1u, (LPDWORD)(v1 + 40));
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
      }
      v1 += 72;
      if ( !*(_QWORD *)v1 )
      {
        if ( v2 )
          return (unsigned int)v2;
        goto LABEL_11;
      }
    }
  }
  else
  {
LABEL_11:
    v4 = off_18002D3B0[0];
    v2 = 1;
    v5 = off_18002D3B8;
    while ( v4 < v5 && v2 >= 0 )
    {
      v6 = *v4;
      if ( *v4 )
      {
        v7 = *(_QWORD *)(v6 + 16) == 0;
        pUnk = 0;
        if ( v7 )
        {
          v2 = 0;
        }
        else
        {
          v2 = (*(__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))(v6 + 16))(
                 *(_QWORD *)(v6 + 24),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &pUnk);
          if ( v2 >= 0 )
            v2 = CoRegisterClassObject(*(const IID *const *)v6, pUnk, 4u, 1u, (LPDWORD)(v6 + 40));
          if ( pUnk )
            ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
          v5 = off_18002D3B8;
        }
      }
      ++v4;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000be4c  mov     [rsp+arg_8], rbx
0x18000be51  mov     [rsp+arg_10], rsi
0x18000be56  mov     [rsp+pUnk], rcx
0x18000be5b  push    rdi
0x18000be5c  sub     rsp, 30h
0x18000be60  mov     rdi, cs:qword_18002E1D8
0x18000be67  test    rdi, rdi
0x18000be6a  jz      loc_18000BEFB
0x18000be70  xor     ebx, ebx
0x18000be72  cmp     [rdi], rbx
0x18000be75  jz      loc_18000BEFB
0x18000be7b  test    ebx, ebx
0x18000be7d  jnz     loc_18000BFA3
0x18000be83  mov     rax, [rdi+10h]
0x18000be87  mov     [rsp+38h+pUnk], 0
0x18000be90  test    rax, rax
0x18000be93  jz      short loc_18000BEE9
0x18000be95  mov     rcx, [rdi+18h]
0x18000be99  lea     r8, [rsp+38h+pUnk]
0x18000be9e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000bea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beaa  mov     ebx, eax
0x18000beac  test    eax, eax
0x18000beae  js      short loc_18000BED3
0x18000beb0  mov     rdx, [rsp+38h+pUnk]; pUnk
0x18000beb5  lea     rax, [rdi+28h]
0x18000beb9  mov     rcx, [rdi]; rclsid
0x18000bebc  mov     r9d, 1; flags
0x18000bec2  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x18000bec7  lea     r8d, [r9+3]; dwClsContext
0x18000becb  call    cs:__imp_CoRegisterClassObject
0x18000bed1  mov     ebx, eax
0x18000bed3  mov     rcx, [rsp+38h+pUnk]
0x18000bed8  test    rcx, rcx
0x18000bedb  jz      short loc_18000BEE9
0x18000bedd  mov     rax, [rcx]
0x18000bee0  mov     rax, [rax+10h]
0x18000bee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bee9  add     rdi, 48h ; 'H'
0x18000beed  cmp     qword ptr [rdi], 0
0x18000bef1  jnz     short loc_18000BE7B
0x18000bef3  test    ebx, ebx
0x18000bef5  jnz     loc_18000BFA3
0x18000befb  mov     rdi, cs:off_18002D3B0
0x18000bf02  mov     ebx, 1
0x18000bf07  mov     rax, cs:off_18002D3B8
0x18000bf0e  jmp     loc_18000BF9A
0x18000bf13  test    ebx, ebx
0x18000bf15  js      loc_18000BFA3
0x18000bf1b  mov     rsi, [rdi]
0x18000bf1e  test    rsi, rsi
0x18000bf21  jz      short loc_18000BF96
0x18000bf23  cmp     qword ptr [rsi+10h], 0
0x18000bf28  mov     [rsp+38h+pUnk], 0
0x18000bf31  jnz     short loc_18000BF37
0x18000bf33  xor     ebx, ebx
0x18000bf35  jmp     short loc_18000BF96
0x18000bf37  mov     rcx, [rsi+18h]
0x18000bf3b  lea     r8, [rsp+38h+pUnk]
0x18000bf40  mov     rax, [rsi+10h]
0x18000bf44  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000bf4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf50  mov     ebx, eax
0x18000bf52  test    eax, eax
0x18000bf54  js      short loc_18000BF79
0x18000bf56  mov     rdx, [rsp+38h+pUnk]; pUnk
0x18000bf5b  lea     rax, [rsi+28h]
0x18000bf5f  mov     rcx, [rsi]; rclsid
0x18000bf62  mov     r9d, 1; flags
0x18000bf68  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x18000bf6d  lea     r8d, [r9+3]; dwClsContext
0x18000bf71  call    cs:__imp_CoRegisterClassObject
0x18000bf77  mov     ebx, eax
0x18000bf79  mov     rcx, [rsp+38h+pUnk]
0x18000bf7e  test    rcx, rcx
0x18000bf81  jz      short loc_18000BF8F
0x18000bf83  mov     rax, [rcx]
0x18000bf86  mov     rax, [rax+10h]
0x18000bf8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf8f  mov     rax, cs:off_18002D3B8
0x18000bf96  add     rdi, 8
0x18000bf9a  cmp     rdi, rax
0x18000bf9d  jb      loc_18000BF13
0x18000bfa3  mov     rsi, [rsp+38h+arg_10]
0x18000bfa8  mov     eax, ebx
0x18000bfaa  mov     rbx, [rsp+38h+arg_8]
0x18000bfaf  add     rsp, 30h
0x18000bfb3  pop     rdi
0x18000bfb4  retn
```
