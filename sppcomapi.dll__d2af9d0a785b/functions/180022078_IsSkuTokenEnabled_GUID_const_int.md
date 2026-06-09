# IsSkuTokenEnabled(_GUID const *,int *)

- ea: `0x180022078`
- end: `0x180022146`
- name: `?IsSkuTokenEnabled@@YAJPEBU_GUID@@PEAH@Z`
- size: `206`
- prototype: `__int64 __fastcall(const struct _GUID *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800236b4`

## callees

- `0x180003520`
- `0x180004288`
- `0x180022078`

## import_xrefs

- `SLC!SLOpen` at `0x1800220a2`
- `SLC!SLOpen` at `0x1800220a2`
- `SLC!SLClose` at `0x180022108`
- `SLC!SLClose` at `0x180022108`
- `sppcext!SLGetTokenActivationGrants` at `0x1800220ca`
- `sppcext!SLGetTokenActivationGrants` at `0x1800220ca`
- `sppcext!SLFreeTokenActivationGrants` at `0x180022127`
- `sppcext!SLFreeTokenActivationGrants` at `0x180022127`

## pseudocode

```c
__int64 __fastcall IsSkuTokenEnabled(const struct _GUID *a1, int *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  HSLC hSLC; // [rsp+40h] [rbp+18h] BYREF
  __int64 v9; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  hSLC = 0;
  v4 = SLOpen(&hSLC);
  v5 = v4;
  if ( v4 < 0 )
    goto LABEL_2;
  v4 = SLGetTokenActivationGrants(hSLC, a1, &v9);
  if ( v4 < 0 )
  {
    if ( v4 != -1073418223 && v4 != -1073417468 )
    {
      v5 = v4;
LABEL_2:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v4);
      goto LABEL_10;
    }
    v6 = 0;
  }
  else
  {
    v6 = 1;
  }
  *a2 = v6;
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( hSLC )
  {
    SLClose(hSLC);
    hSLC = 0;
  }
  if ( v9 )
    SLFreeTokenActivationGrants();
  return v5;
}

```

## disassembly

```asm
0x180022078  mov     rax, rsp
0x18002207b  mov     [rax+8], rbx
0x18002207f  mov     [rax+10h], rsi
0x180022083  push    rdi
0x180022084  sub     rsp, 20h
0x180022088  mov     rsi, rcx
0x18002208b  mov     qword ptr [rax+20h], 0
0x180022093  lea     rcx, [rax+18h]; phSLC
0x180022097  mov     qword ptr [rax+18h], 0
0x18002209f  mov     rdi, rdx
0x1800220a2  call    cs:__imp_SLOpen
0x1800220a9  nop     dword ptr [rax+rax+00h]
0x1800220ae  mov     ebx, eax
0x1800220b0  test    eax, eax
0x1800220b2  jns     short loc_1800220BD
0x1800220b4  mov     ecx, eax
0x1800220b6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800220bb  jmp     short loc_1800220F7
0x1800220bd  mov     rcx, [rsp+28h+hSLC]
0x1800220c2  lea     r8, [rsp+28h+arg_18]
0x1800220c7  mov     rdx, rsi
0x1800220ca  call    cs:__imp_SLGetTokenActivationGrants
0x1800220d1  nop     dword ptr [rax+rax+00h]
0x1800220d6  test    eax, eax
0x1800220d8  js      short loc_1800220E1
0x1800220da  mov     eax, 1
0x1800220df  jmp     short loc_1800220F5
0x1800220e1  cmp     eax, 0C004F011h
0x1800220e6  jz      short loc_1800220F3
0x1800220e8  cmp     eax, 0C004F304h
0x1800220ed  jz      short loc_1800220F3
0x1800220ef  mov     ebx, eax
0x1800220f1  jmp     short loc_1800220B4
0x1800220f3  xor     eax, eax
0x1800220f5  mov     [rdi], eax
0x1800220f7  mov     ecx, ebx
0x1800220f9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800220fe  mov     rcx, [rsp+28h+hSLC]; hSLC
0x180022103  test    rcx, rcx
0x180022106  jz      short loc_18002211D
0x180022108  call    cs:__imp_SLClose
0x18002210f  nop     dword ptr [rax+rax+00h]
0x180022114  mov     [rsp+28h+hSLC], 0
0x18002211d  mov     rcx, [rsp+28h+arg_18]
0x180022122  test    rcx, rcx
0x180022125  jz      short loc_180022133
0x180022127  call    cs:__imp_SLFreeTokenActivationGrants
0x18002212e  nop     dword ptr [rax+rax+00h]
0x180022133  mov     rsi, [rsp+28h+arg_8]
0x180022138  mov     eax, ebx
0x18002213a  mov     rbx, [rsp+28h+arg_0]
0x18002213f  add     rsp, 20h
0x180022143  pop     rdi
0x180022144  retn
```
