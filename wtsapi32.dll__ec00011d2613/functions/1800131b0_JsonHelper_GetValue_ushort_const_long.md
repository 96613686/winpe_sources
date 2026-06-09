# JsonHelper::GetValue(ushort const *,long *)

- ea: `0x1800131b0`
- end: `0x180013280`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAJ@Z`
- size: `208`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012230`
- `0x1800131b0`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## string_xrefs

- `0x180013230`: `m_spJsonObj->GetNamedNumber failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, int *a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, double *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  int ActivityIdPrefix; // eax
  double v11; // [rsp+30h] [rbp-58h] BYREF
  const unsigned __int16 *v12; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v13[32]; // [rsp+40h] [rbp-48h] BYREF

  v3 = *((_QWORD *)this + 7);
  v11 = 0.0;
  v12 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)v3 + 88LL);
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v13, &v12);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &v11);
  if ( v8 >= 0 )
  {
    *a3 = (int)v11;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v7);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      ActivityIdPrefix,
      (__int64)"m_spJsonObj->GetNamedNumber failed!",
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800131b0  push    rbx
0x1800131b2  push    rsi
0x1800131b3  push    rdi
0x1800131b4  sub     rsp, 70h
0x1800131b8  mov     rax, cs:__security_cookie
0x1800131bf  xor     rax, rsp
0x1800131c2  mov     [rsp+88h+var_28], rax
0x1800131c7  mov     rdi, [rcx+38h]
0x1800131cb  xorps   xmm0, xmm0
0x1800131ce  movsd   [rsp+88h+var_58], xmm0
0x1800131d4  lea     rcx, [rsp+88h+var_48]
0x1800131d9  mov     [rsp+88h+var_50], rdx
0x1800131de  mov     rsi, r8
0x1800131e1  lea     rdx, [rsp+88h+var_50]
0x1800131e6  mov     rax, [rdi]
0x1800131e9  mov     rbx, [rax+58h]
0x1800131ed  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800131f2  lea     r8, [rsp+88h+var_58]
0x1800131f7  mov     rcx, rdi
0x1800131fa  mov     rdx, [rax+18h]
0x1800131fe  mov     rax, rbx
0x180013201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013206  mov     ebx, eax
0x180013208  test    eax, eax
0x18001320a  jns     short loc_180013261
0x18001320c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013213  lea     rax, WPP_GLOBAL_Control
0x18001321a  cmp     rcx, rax
0x18001321d  jz      short loc_180013269
0x18001321f  test    byte ptr [rcx+1Ch], 8
0x180013223  jz      short loc_180013269
0x180013225  cmp     byte ptr [rcx+19h], 2
0x180013229  jb      short loc_180013269
0x18001322b  call    RdpX_GetActivityIdPrefix
0x180013230  lea     rcx, aMSpjsonobjGetn_0; "m_spJsonObj->GetNamedNumber failed!"
0x180013237  mov     [rsp+88h+var_60], ebx
0x18001323b  mov     [rsp+88h+var_68], rcx
0x180013240  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180013247  mov     rcx, cs:WPP_GLOBAL_Control
0x18001324e  mov     edx, 27h ; '''
0x180013253  mov     r9d, eax
0x180013256  mov     rcx, [rcx+10h]
0x18001325a  call    WPP_SF_DsD
0x18001325f  jmp     short loc_180013269
0x180013261  cvttsd2si eax, [rsp+88h+var_58]
0x180013267  mov     [rsi], eax
0x180013269  mov     eax, ebx
0x18001326b  mov     rcx, [rsp+88h+var_28]
0x180013270  xor     rcx, rsp; StackCookie
0x180013273  call    __security_check_cookie
0x180013278  add     rsp, 70h
0x18001327c  pop     rdi
0x18001327d  pop     rsi
0x18001327e  pop     rbx
0x18001327f  retn
```
