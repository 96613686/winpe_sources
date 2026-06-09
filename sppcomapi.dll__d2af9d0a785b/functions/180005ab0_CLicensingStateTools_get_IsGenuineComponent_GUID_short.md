# CLicensingStateTools::get_IsGenuineComponent(_GUID *,short *)

- ea: `0x180005ab0`
- end: `0x180005b27`
- name: `?get_IsGenuineComponent@CLicensingStateTools@@UEAAJPEAU_GUID@@PEAF@Z`
- size: `119`
- prototype: `int(CLicensingStateTools *__hidden this, struct _GUID *, __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180005ab0`

## import_xrefs

- `SLWGA!SLIsGenuineLocal` at `0x180005aeb`
- `SLWGA!SLIsGenuineLocal` at `0x180005aeb`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_IsGenuineComponent(
        CLicensingStateTools *this,
        struct _GUID *a2,
        __int16 *a3)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  HRESULT v6; // eax
  __int16 v7; // ax
  SL_GENUINE_STATE pGenuineState; // [rsp+38h] [rbp+10h] BYREF

  pGenuineState = SL_GEN_STATE_IS_GENUINE;
  if ( !a2 || !a3 )
  {
    v4 = 2147942487LL;
    v5 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_11;
  }
  v6 = SLIsGenuineLocal(a2, &pGenuineState, 0);
  v5 = v6;
  if ( v6 < 0 )
  {
    v4 = (unsigned int)v6;
    goto LABEL_3;
  }
  if ( pGenuineState )
    v7 = 0;
  else
    v7 = -1;
  *a3 = v7;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x180005ab0  mov     [rsp+arg_0], rbx
0x180005ab5  push    rdi
0x180005ab6  sub     rsp, 20h
0x180005aba  mov     [rsp+28h+pGenuineState], 0
0x180005ac2  mov     rdi, r8
0x180005ac5  mov     rax, rdx
0x180005ac8  test    rdx, rdx
0x180005acb  jnz     short loc_180005ADB
0x180005acd  mov     ecx, 80070057h
0x180005ad2  mov     ebx, ecx
0x180005ad4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180005ad9  jmp     short loc_180005B12
0x180005adb  test    rdi, rdi
0x180005ade  jz      short loc_180005ACD
0x180005ae0  xor     r8d, r8d; pUIOptions
0x180005ae3  lea     rdx, [rsp+28h+pGenuineState]; pGenuineState
0x180005ae8  mov     rcx, rax; pAppId
0x180005aeb  call    cs:__imp_SLIsGenuineLocal
0x180005af2  nop     dword ptr [rax+rax+00h]
0x180005af7  mov     ebx, eax
0x180005af9  test    eax, eax
0x180005afb  jns     short loc_180005B01
0x180005afd  mov     ecx, eax
0x180005aff  jmp     short loc_180005AD4
0x180005b01  cmp     [rsp+28h+pGenuineState], 0
0x180005b06  jnz     short loc_180005B0D
0x180005b08  or      eax, 0FFFFFFFFh
0x180005b0b  jmp     short loc_180005B0F
0x180005b0d  xor     eax, eax
0x180005b0f  mov     [rdi], ax
0x180005b12  mov     ecx, ebx
0x180005b14  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180005b19  mov     eax, ebx
0x180005b1b  mov     rbx, [rsp+28h+arg_0]
0x180005b20  add     rsp, 20h
0x180005b24  pop     rdi
0x180005b25  retn
```
