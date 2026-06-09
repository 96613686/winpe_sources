# CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(int,CComObjectActivationT<CEmptyType> *)

- ea: `0x18001cc48`
- end: `0x18001cd7c`
- name: `?Insert@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJHPEAU?$CComObjectActivationT@VCEmptyType@@@@@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001ca2c`

## callees

- `0x1800032a0`
- `0x180003318`
- `0x180003520`
- `0x180004288`
- `0x18001cc48`
- `0x18001d750`
- `0x18003c51e`

## pseudocode

```c
__int64 __fastcall CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::Insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  __int64 v5; // rcx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  int v11; // edi
  int v12; // ebx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  int v18; // [rsp+40h] [rbp+8h] BYREF
  int v19; // [rsp+58h] [rbp+20h] BYREF

  v4 = (int)a2;
  v5 = *(unsigned int *)(a1 + 4);
  v19 = 0;
  if ( (int)v5 < 0 )
  {
    v7 = -2147418113;
    v8 = 2147549183LL;
LABEL_5:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_27;
  }
  v9 = SafeAdd<int>(v5, a2, &v19);
  v7 = v9;
  if ( v9 < 0 )
  {
    v8 = (unsigned int)v9;
    goto LABEL_5;
  }
  v11 = *(_DWORD *)a1;
  if ( *(int *)a1 >= 0 )
  {
    if ( v19 <= v11 )
    {
      v12 = 0;
      goto LABEL_22;
    }
    v18 = *(_DWORD *)a1;
    do
    {
      if ( v11 )
      {
        v14 = SafeMul<int>((unsigned int)v11, v10, &v18);
        v12 = v14;
        if ( v14 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
        v11 = v18;
      }
      else
      {
        v11 = 32;
        v12 = 0;
        v18 = 32;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v12 < 0 )
      {
        v13 = (unsigned int)v12;
        goto LABEL_21;
      }
    }
    while ( v11 < v19 );
    v15 = CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(
            a1,
            (unsigned int)v11);
    v12 = v15;
    if ( v15 >= 0 )
      goto LABEL_22;
    v13 = (unsigned int)v15;
  }
  else
  {
    v12 = -2147418113;
    v13 = 2147549183LL;
  }
LABEL_21:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
LABEL_22:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( v12 < 0 )
  {
    v7 = v12;
    v8 = (unsigned int)v12;
    goto LABEL_5;
  }
  v16 = *(_DWORD *)(a1 + 4);
  if ( (int)v4 < v16 )
    memmove_0(
      (void *)(*(_QWORD *)(a1 + 8) + 8 * v4 + 8),
      (const void *)(*(_QWORD *)(a1 + 8) + 8 * v4),
      8LL * (v16 - (int)v4));
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4) = 0;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v4) = a3;
  ++*(_DWORD *)(a1 + 4);
  v7 = 0;
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return v7;
}

```

## disassembly

```asm
0x18001cc48  mov     [rsp+arg_8], rbx
0x18001cc4d  mov     [rsp+arg_10], rbp
0x18001cc52  push    rsi
0x18001cc53  push    rdi
0x18001cc54  push    r14
0x18001cc56  sub     rsp, 20h
0x18001cc5a  mov     rsi, rcx
0x18001cc5d  movsxd  rbp, edx
0x18001cc60  mov     ecx, [rcx+4]
0x18001cc63  mov     r14, r8
0x18001cc66  mov     [rsp+38h+arg_18], 0
0x18001cc6e  test    ecx, ecx
0x18001cc70  jns     short loc_18001CC7B
0x18001cc72  mov     edi, 8000FFFFh
0x18001cc77  mov     ecx, edi
0x18001cc79  jmp     short loc_18001CC8D
0x18001cc7b  lea     r8, [rsp+38h+arg_18]
0x18001cc80  call    ??$SafeAdd@H@@YAJHHPEAH@Z; SafeAdd<int>(int,int,int *)
0x18001cc85  mov     edi, eax
0x18001cc87  test    eax, eax
0x18001cc89  jns     short loc_18001CC97
0x18001cc8b  mov     ecx, eax
0x18001cc8d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cc92  jmp     loc_18001CD5F
0x18001cc97  mov     edi, [rsi]
0x18001cc99  test    edi, edi
0x18001cc9b  jns     short loc_18001CCA8
0x18001cc9d  mov     edi, 8000FFFFh
0x18001cca2  mov     ebx, edi
0x18001cca4  mov     ecx, edi
0x18001cca6  jmp     short loc_18001CD0B
0x18001cca8  cmp     [rsp+38h+arg_18], edi
0x18001ccac  jg      short loc_18001CCB2
0x18001ccae  xor     ebx, ebx
0x18001ccb0  jmp     short loc_18001CD10
0x18001ccb2  mov     [rsp+38h+arg_0], edi
0x18001ccb6  test    edi, edi
0x18001ccb8  jnz     short loc_18001CCC7
0x18001ccba  mov     edi, 20h ; ' '
0x18001ccbf  xor     ebx, ebx
0x18001ccc1  mov     [rsp+38h+arg_0], edi
0x18001ccc5  jmp     short loc_18001CCE4
0x18001ccc7  lea     r8, [rsp+38h+arg_0]
0x18001cccc  mov     ecx, edi
0x18001ccce  call    ??$SafeMul@H@@YAJHHPEAH@Z; SafeMul<int>(int,int,int *)
0x18001ccd3  mov     ebx, eax
0x18001ccd5  test    eax, eax
0x18001ccd7  jns     short loc_18001CCE0
0x18001ccd9  mov     ecx, eax
0x18001ccdb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cce0  mov     edi, [rsp+38h+arg_0]
0x18001cce4  mov     ecx, ebx
0x18001cce6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cceb  test    ebx, ebx
0x18001cced  js      short loc_18001CD09
0x18001ccef  cmp     edi, [rsp+38h+arg_18]
0x18001ccf3  jl      short loc_18001CCB6
0x18001ccf5  mov     edx, edi
0x18001ccf7  mov     rcx, rsi
0x18001ccfa  call    ?SetSize@?$CArray@PEAU?$CComObjectActivationT@VCEmptyType@@@@U_GUID@@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<CComObjectActivationT<CEmptyType> *,_GUID,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18001ccff  mov     ebx, eax
0x18001cd01  test    eax, eax
0x18001cd03  jns     short loc_18001CD10
0x18001cd05  mov     ecx, eax
0x18001cd07  jmp     short loc_18001CD0B
0x18001cd09  mov     ecx, ebx
0x18001cd0b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cd10  mov     ecx, ebx
0x18001cd12  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cd17  test    ebx, ebx
0x18001cd19  jns     short loc_18001CD24
0x18001cd1b  mov     edi, ebx
0x18001cd1d  mov     ecx, ebx
0x18001cd1f  jmp     loc_18001CC8D
0x18001cd24  mov     ecx, [rsi+4]
0x18001cd27  mov     rbx, rbp
0x18001cd2a  cmp     ebp, ecx
0x18001cd2c  jge     short loc_18001CD48
0x18001cd2e  mov     rax, [rsi+8]
0x18001cd32  sub     ecx, ebp
0x18001cd34  movsxd  r8, ecx
0x18001cd37  shl     r8, 3; Size
0x18001cd3b  lea     rdx, [rax+rbp*8]; Src
0x18001cd3f  lea     rcx, [rdx+8]; void *
0x18001cd43  call    memmove_0
0x18001cd48  mov     rax, [rsi+8]
0x18001cd4c  xor     ecx, ecx
0x18001cd4e  mov     [rax+rbx*8], rcx
0x18001cd52  mov     rax, [rsi+8]
0x18001cd56  mov     [rax+rbx*8], r14
0x18001cd5a  inc     dword ptr [rsi+4]
0x18001cd5d  xor     edi, edi
0x18001cd5f  mov     ecx, edi
0x18001cd61  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cd66  mov     rbx, [rsp+38h+arg_8]
0x18001cd6b  mov     eax, edi
0x18001cd6d  mov     rbp, [rsp+38h+arg_10]
0x18001cd72  add     rsp, 20h
0x18001cd76  pop     r14
0x18001cd78  pop     rdi
0x18001cd79  pop     rsi
0x18001cd7a  retn
```
