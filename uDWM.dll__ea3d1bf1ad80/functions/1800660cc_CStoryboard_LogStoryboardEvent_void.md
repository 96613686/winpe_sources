# CStoryboard::_LogStoryboardEvent(void)

- ea: `0x1800660cc`
- end: `0x18006626a`
- name: `?_LogStoryboardEvent@CStoryboard@@IEAAXXZ`
- size: `414`
- prototype: `void __fastcall(CStoryboard *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028444`
- `0x18002d650`
- `0x180066070`
- `0x1800660a8`
- `0x1800c2a4c`

## callees

- `0x180050dfc`
- `0x1800660cc`
- `0x180095130`
- `0x180095b28`
- `0x1800c8ed4`
- `0x1800ea010`

## import_xrefs

- `dcomp!__imp_GetAnimationScenarioNameFromGUID` at `0x1800661b3`
- `dcomp!__imp_GetAnimationScenarioNameFromGUID` at `0x1800661b3`
- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x18006617b`
- `dcomp!__imp_DCompositionCreateAnimationStats` at `0x18006617b`

## pseudocode

```c
void __fastcall CStoryboard::_LogStoryboardEvent(CStoryboard *this, __int64 a2)
{
  int v3; // ebx
  _QWORD *v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, _BYTE *, _QWORD, _QWORD, _BYTE *, _QWORD, int); // rbx
  int v8; // eax
  _BYTE Buf2[28]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD Buf1[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v11[128]; // [rsp+80h] [rbp-80h] BYREF

  if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
    McTemplateU0qd_EtwEventWriteTransfer(this, a2, *((unsigned int *)this + 6), *((unsigned int *)this + 7));
  if ( *((_DWORD *)this + 7) != -1 )
  {
    v3 = *((_DWORD *)this + 6);
    if ( (unsigned int)(v3 - 3) <= 1 )
    {
      *(_OWORD *)Buf2 = 0;
      Buf1[0] = *((_OWORD *)this + 2);
      if ( memcmp_0(Buf1, Buf2, 0x10u) )
      {
        v4 = (_QWORD *)((char *)this + 80);
        if ( v3 == 3 )
        {
          wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset((char *)this + 80);
          if ( (int)DCompositionCreateAnimationStats((char *)this + 80) >= 0 )
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 24LL))(*v4, 0);
        }
        else if ( *v4 )
        {
          GetAnimationScenarioNameFromGUID((char *)this + 32, v11, 64);
          v5 = *v4;
          memset(Buf1, 0, 28);
          if ( (*(int (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v5 + 88LL))(v5, Buf1) >= 0 )
          {
            v6 = *v4;
            v7 = *(void (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD, _BYTE *, _QWORD, int))(*(_QWORD *)*v4 + 216LL);
            v8 = (*(__int64 (__fastcall **)(CStoryboard *))(*(_QWORD *)this + 32LL))(this);
            *(_OWORD *)Buf2 = Buf1[0];
            *(_OWORD *)&Buf2[12] = *(_OWORD *)((char *)Buf1 + 12);
            v7(v6, Buf2, 0, 0, v11, 0, v8);
          }
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 40LL))(*v4, 0);
          wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset((char *)this + 80);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800660cc  mov     [rsp-8+arg_8], rbx
0x1800660d1  mov     [rsp-8+arg_10], rsi
0x1800660d6  push    rbp
0x1800660d7  push    rdi
0x1800660d8  push    r14
0x1800660da  lea     rbp, [rsp-10h]
0x1800660df  sub     rsp, 110h
0x1800660e6  mov     rax, cs:__security_cookie
0x1800660ed  xor     rax, rsp
0x1800660f0  mov     [rbp+20h+var_20], rax
0x1800660f4  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, 1
0x1800660fb  mov     r14, rcx
0x1800660fe  jnz     loc_180066258
0x180066104  cmp     dword ptr [r14+1Ch], 0FFFFFFFFh
0x180066109  jnz     short loc_18006612F
0x18006610b  mov     rcx, [rbp+20h+var_20]
0x18006610f  xor     rcx, rsp; StackCookie
0x180066112  call    __security_check_cookie
0x180066117  lea     r11, [rsp+120h+var_10]
0x18006611f  mov     rbx, [r11+28h]
0x180066123  mov     rsi, [r11+30h]
0x180066127  mov     rsp, r11
0x18006612a  pop     r14
0x18006612c  pop     rdi
0x18006612d  pop     rbp
0x18006612e  retn
0x18006612f  mov     ebx, [r14+18h]
0x180066133  lea     eax, [rbx-3]
0x180066136  cmp     eax, 1
0x180066139  ja      short loc_18006610B
0x18006613b  xorps   xmm0, xmm0
0x18006613e  lea     rdx, [rsp+120h+Buf2]; Buf2
0x180066143  movups  [rsp+120h+Buf2], xmm0
0x180066148  mov     r8d, 10h; Size
0x18006614e  lea     rcx, [rsp+120h+Buf1]; Buf1
0x180066153  movups  xmm0, xmmword ptr [r14+20h]
0x180066158  movdqu  [rsp+120h+Buf1], xmm0
0x18006615e  call    memcmp_0
0x180066163  test    eax, eax
0x180066165  jz      short loc_18006610B
0x180066167  lea     rsi, [r14+50h]
0x18006616b  cmp     ebx, 3
0x18006616e  jnz     short loc_18006619B
0x180066170  mov     rcx, rsi
0x180066173  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x180066178  mov     rcx, rsi
0x18006617b  call    cs:__imp_DCompositionCreateAnimationStats
0x180066181  test    eax, eax
0x180066183  js      short loc_18006610B
0x180066185  mov     rcx, [rsi]
0x180066188  xor     edx, edx
0x18006618a  mov     rax, [rcx]
0x18006618d  mov     rax, [rax+18h]
0x180066191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066196  jmp     loc_18006610B
0x18006619b  cmp     qword ptr [rsi], 0
0x18006619f  jz      loc_18006610B
0x1800661a5  mov     r8d, 40h ; '@'
0x1800661ab  lea     rdx, [rbp+20h+var_A0]
0x1800661af  lea     rcx, [r14+20h]
0x1800661b3  call    cs:__imp_GetAnimationScenarioNameFromGUID
0x1800661b9  mov     rcx, [rsi]
0x1800661bc  lea     rdx, [rsp+120h+Buf1]
0x1800661c1  xorps   xmm0, xmm0
0x1800661c4  movups  [rsp+120h+Buf1], xmm0
0x1800661c9  movups  [rsp+120h+Buf1+0Ch], xmm0
0x1800661ce  mov     rax, [rcx]
0x1800661d1  mov     rax, [rax+58h]
0x1800661d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661da  test    eax, eax
0x1800661dc  js      short loc_18006623A
0x1800661de  mov     rdi, [rsi]
0x1800661e1  mov     rcx, r14
0x1800661e4  mov     rax, [rdi]
0x1800661e7  mov     rbx, [rax+0D8h]
0x1800661ee  mov     rax, [r14]
0x1800661f1  mov     rax, [rax+20h]
0x1800661f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800661fa  movups  xmm0, [rsp+120h+Buf1]
0x1800661ff  mov     [rsp+120h+var_F0], eax
0x180066203  lea     rax, [rbp+20h+var_A0]
0x180066207  movups  xmm1, [rsp+120h+Buf1+0Ch]
0x18006620c  lea     rdx, [rsp+120h+Buf2]
0x180066211  mov     [rsp+120h+var_F8], 0
0x18006621a  movaps  [rsp+120h+Buf2], xmm0
0x18006621f  xor     r9d, r9d
0x180066222  mov     [rsp+120h+var_100], rax
0x180066227  xor     r8d, r8d
0x18006622a  mov     rax, rbx
0x18006622d  mov     rcx, rdi
0x180066230  movups  [rsp+120h+Buf2+0Ch], xmm1
0x180066235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006623a  mov     rcx, [rsi]
0x18006623d  xor     edx, edx
0x18006623f  mov     rax, [rcx]
0x180066242  mov     rax, [rax+28h]
0x180066246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006624b  mov     rcx, rsi
0x18006624e  call    ?reset@?$com_ptr_t@UICompositionSurface@Composition@UI@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::UI::Composition::ICompositionSurface,wil::err_returncode_policy>::reset(void)
0x180066253  jmp     loc_18006610B
0x180066258  mov     r9d, [rcx+1Ch]
0x18006625c  mov     r8d, [rcx+18h]
0x180066260  call    McTemplateU0qd_EtwEventWriteTransfer
0x180066265  jmp     loc_180066104
```
