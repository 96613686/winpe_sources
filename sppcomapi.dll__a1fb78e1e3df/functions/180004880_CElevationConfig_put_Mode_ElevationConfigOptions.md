# CElevationConfig::put_Mode(_ElevationConfigOptions)

- ea: `0x180004880`
- end: `0x18000491d`
- name: `?put_Mode@CElevationConfig@@UEAAJW4_ElevationConfigOptions@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x180003e14`
- `0x180004288`
- `0x180004880`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CElevationConfig::put_Mode(__int64 a1, int a2)
{
  unsigned int v2; // ebx
  __int64 v5; // rcx
  int Elevated; // eax
  struct ISPPLUA *v8; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v8 = 0;
  if ( *(_DWORD *)(a1 + 136) != a2 )
  {
    v5 = *(_QWORD *)(a1 + 144);
    if ( v5 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *(_QWORD *)(a1 + 144) = 0;
    }
    if ( a2 == 1 && (Elevated = CElevationConfig::GetElevated((CElevationConfig *)a1, &v8), v2 = Elevated, Elevated < 0) )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Elevated);
    else
      *(_DWORD *)(a1 + 136) = a2;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  if ( v8 )
    (*(void (__fastcall **)(struct ISPPLUA *))(*(_QWORD *)v8 + 16LL))(v8);
  return v2;
}

```

## disassembly

```asm
0x180004880  mov     [rsp+arg_8], rbx
0x180004885  mov     [rsp+arg_10], rsi
0x18000488a  push    rdi
0x18000488b  sub     rsp, 20h
0x18000488f  xor     ebx, ebx
0x180004891  mov     [rsp+28h+arg_0], 0
0x18000489a  mov     esi, edx
0x18000489c  mov     rdi, rcx
0x18000489f  cmp     [rcx+88h], edx
0x1800048a5  jz      short loc_1800048ED
0x1800048a7  mov     rcx, [rcx+90h]
0x1800048ae  test    rcx, rcx
0x1800048b1  jz      short loc_1800048C6
0x1800048b3  mov     rax, [rcx]
0x1800048b6  mov     rax, [rax+10h]
0x1800048ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048bf  mov     [rdi+90h], rbx
0x1800048c6  cmp     esi, 1
0x1800048c9  jnz     short loc_1800048E7
0x1800048cb  lea     rdx, [rsp+28h+arg_0]; struct ISPPLUA **
0x1800048d0  mov     rcx, rdi; this
0x1800048d3  call    ?GetElevated@CElevationConfig@@QEAAJPEAPEAUISPPLUA@@@Z; CElevationConfig::GetElevated(ISPPLUA * *)
0x1800048d8  mov     ebx, eax
0x1800048da  test    eax, eax
0x1800048dc  jns     short loc_1800048E7
0x1800048de  mov     ecx, eax
0x1800048e0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800048e5  jmp     short loc_1800048ED
0x1800048e7  mov     [rdi+88h], esi
0x1800048ed  mov     ecx, ebx
0x1800048ef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800048f4  mov     rcx, [rsp+28h+arg_0]
0x1800048f9  test    rcx, rcx
0x1800048fc  jz      short loc_18000490A
0x1800048fe  mov     rax, [rcx]
0x180004901  mov     rax, [rax+10h]
0x180004905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490a  mov     rsi, [rsp+28h+arg_10]
0x18000490f  mov     eax, ebx
0x180004911  mov     rbx, [rsp+28h+arg_8]
0x180004916  add     rsp, 20h
0x18000491a  pop     rdi
0x18000491b  retn
```
