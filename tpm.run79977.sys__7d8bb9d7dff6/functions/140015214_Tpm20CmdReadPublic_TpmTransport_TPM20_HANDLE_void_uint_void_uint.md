# Tpm20CmdReadPublic(TpmTransport *,_TPM20_HANDLE,void *,uint *,void *,uint *)

- ea: `0x140015214`
- end: `0x1400155f2`
- name: `?Tpm20CmdReadPublic@@YAJPEAVTpmTransport@@T_TPM20_HANDLE@@PEAXPEAI23@Z`
- size: `990`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002aaa0`

## callees

- `0x1400078b8`
- `0x140009278`
- `0x140009660`
- `0x14000f410`
- `0x140015214`
- `0x14001a770`
- `0x140039740`
- `0x140039840`
- `0x140039b40`

## pseudocode

```c
__int64 __fastcall Tpm20CmdReadPublic(TpmTransport *a1, unsigned int a2, void *a3, _DWORD *a4, void *a5, _DWORD *a6)
{
  int v10; // ebx
  unsigned int v11; // edx
  signed int v12; // r9d
  int v13; // esp
  __int64 v14; // rcx
  __int64 v15; // r10
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // ebx
  size_t v19; // r8
  __int64 v20; // r9
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  int v23; // ebx
  __int64 v24; // r9
  void *v25; // rdx
  size_t v26; // r8
  _WORD v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-BCh] BYREF
  _WORD *v30; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B0h]
  void *v32; // [rsp+58h] [rbp-A8h]
  __int16 v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+62h] [rbp-9Eh]
  int v35; // [rsp+66h] [rbp-9Ah]
  unsigned __int32 v36; // [rsp+6Ah] [rbp-96h]
  _WORD v37[264]; // [rsp+70h] [rbp-90h] BYREF

  memset(v37, 0, 0x20Au);
  v28[0] = 0;
  v33 = 384;
  v34 = 234881024;
  v35 = 1929445376;
  v36 = _byteswap_ulong(a2);
  v29 = 522;
  v10 = TpmTransport::DispatchCommand(a1, (char *)&v33, 0xEu, (char *)v37, &v29, 1, 0);
  if ( v10 >= 0 )
  {
    v11 = v29;
    v12 = *(_DWORD *)&v37[3];
    if ( v29 < 0xA
      || _byteswap_ulong(*(unsigned int *)&v37[1]) < v29
      || v37[0] != 384
      || *(_DWORD *)&v37[3]
      || v29 > 0x20A )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          46,
          WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids,
          _byteswap_ulong(*(unsigned int *)&v37[3]));
      return (unsigned int)-1073741823;
    }
    v31 = v29;
    v30 = v37;
    v14 = v13 + 122 - (unsigned int)v37;
    if ( (int)v14 + 2 < (unsigned int)v14 || (v15 = (unsigned int)v14, v14 + 2 > (unsigned __int64)v29) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        return (unsigned int)-1073741823;
      v22 = 48;
    }
    else
    {
      do
      {
        v16 = v12;
        v17 = v15 - v12++;
        *((_BYTE *)v28 + v16) = *((_BYTE *)v37 + v17 + 1);
      }
      while ( (unsigned int)v12 < 2 );
      v18 = v28[0];
      if ( v28[0] > v11 + (unsigned int)v37 - (unsigned int)&v37[6] )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          return (unsigned int)-1073741823;
        v22 = 49;
      }
      else
      {
        v19 = v28[0];
        v32 = (char *)&v37[6] + v28[0];
        v20 = (unsigned int)*a4;
        if ( (unsigned int)v20 < v28[0] )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, v20);
          }
          *a4 = v18;
          return (unsigned int)-2147483643;
        }
        *a4 = v28[0];
        memmove(a3, &v37[6], v19);
        if ( (int)TpmBufferAccessor::Get<unsigned short>(&v30, v28, 0) >= 0 )
        {
          v23 = v28[0];
          if ( v28[0] <= v31 + (_DWORD)v30 - (_DWORD)v32 )
          {
            v24 = (unsigned int)*a6;
            if ( (unsigned int)v24 >= v28[0] )
            {
              v25 = v32;
              v26 = v28[0];
              *a6 = v28[0];
              memmove(a5, v25, v26);
              return 0;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, v24);
            }
            *a6 = v23;
            return (unsigned int)-2147483643;
          }
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            return (unsigned int)-1073741823;
          }
          v22 = 52;
        }
        else
        {
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            return (unsigned int)-1073741823;
          }
          v22 = 51;
        }
      }
    }
    WPP_SF_(v21->AttachedDevice, v22, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids);
    return (unsigned int)-1073741823;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140015214  push    rbp
0x140015216  push    rbx
0x140015217  push    rsi
0x140015218  push    rdi
0x140015219  push    r12
0x14001521b  push    r14
0x14001521d  push    r15
0x14001521f  lea     rbp, [rsp-190h]
0x140015227  sub     rsp, 290h
0x14001522e  mov     rax, cs:__security_cookie
0x140015235  xor     rax, rsp
0x140015238  mov     [rbp+1C0h+var_40], rax
0x14001523f  mov     r15, [rbp+1C0h+arg_20]
0x140015246  mov     r12, r8
0x140015249  mov     rsi, [rbp+1C0h+arg_28]
0x140015250  mov     ebx, edx
0x140015252  mov     rdi, rcx
0x140015255  xor     edx, edx; Val
0x140015257  mov     r8d, 20Ah; Size
0x14001525d  lea     rcx, [rsp+2C0h+var_250]; void *
0x140015262  mov     r14, r9
0x140015265  call    memset
0x14001526a  xor     eax, eax
0x14001526c  mov     [rsp+2C0h+var_290], 0; struct TpmTransport::TpmTimeouts *
0x140015275  mov     [rsp+2C0h+var_280], ax
0x14001527a  lea     r9, [rsp+2C0h+var_250]; void *
0x14001527f  mov     eax, 180h
0x140015284  mov     [rsp+2C0h+var_298], 1; int
0x14001528c  mov     [rsp+2C0h+var_260], ax
0x140015291  lea     rdx, [rsp+2C0h+var_260]; void *
0x140015296  lea     rax, [rsp+2C0h+var_27C]
0x14001529b  mov     [rsp+2C0h+var_25E], 0E000000h
0x1400152a3  bswap   ebx
0x1400152a5  mov     r8d, 0Eh; unsigned int
0x1400152ab  mov     [rsp+2C0h+var_2A0], rax; unsigned int *
0x1400152b0  mov     rcx, rdi; this
0x1400152b3  mov     [rsp+2C0h+var_25A], 73010000h
0x1400152bb  mov     [rsp+2C0h+var_256], ebx
0x1400152bf  mov     [rsp+2C0h+var_27C], 20Ah
0x1400152c7  call    ?DispatchCommand@TpmTransport@@QEAAJPEAXI0PEAIHPEAVTpmTimeouts@1@@Z; TpmTransport::DispatchCommand(void *,uint,void *,uint *,int,TpmTransport::TpmTimeouts *)
0x1400152cc  mov     ebx, eax
0x1400152ce  test    eax, eax
0x1400152d0  jns     short loc_140015312
0x1400152d2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400152d9  lea     rax, WPP_GLOBAL_Control
0x1400152e0  cmp     rcx, rax
0x1400152e3  jz      loc_1400155CE
0x1400152e9  mov     edx, [rcx+2Ch]
0x1400152ec  test    dl, 1
0x1400152ef  jz      loc_1400155CE
0x1400152f5  mov     rcx, [rcx+18h]
0x1400152f9  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x140015300  mov     edx, 2Dh ; '-'
0x140015305  mov     r9d, ebx
0x140015308  call    WPP_SF_d
0x14001530d  jmp     loc_1400155CE
0x140015312  mov     edx, [rsp+2C0h+var_27C]
0x140015316  mov     r9d, [rsp+2C0h+var_24A]
0x14001531b  cmp     edx, 0Ah
0x14001531e  jb      loc_140015597
0x140015324  mov     eax, [rsp+2C0h+var_24E]
0x140015328  bswap   eax
0x14001532a  cmp     eax, edx
0x14001532c  jb      loc_140015597
0x140015332  mov     eax, 180h
0x140015337  cmp     [rsp+2C0h+var_250], ax
0x14001533c  jnz     loc_140015597
0x140015342  test    r9d, r9d
0x140015345  jnz     loc_140015597
0x14001534b  cmp     edx, 20Ah
0x140015351  ja      loc_140015597
0x140015357  lea     r8, [rsp+2C0h+var_250]
0x14001535c  mov     [rsp+2C0h+var_270], edx
0x140015360  lea     rax, [rsp+2C0h+var_250]
0x140015365  mov     [rsp+2C0h+var_278], r8
0x14001536a  mov     ecx, edx
0x14001536c  sub     ecx, eax
0x14001536e  add     ecx, r8d
0x140015371  cmp     ecx, 0Ah
0x140015374  jb      loc_140015573
0x14001537a  lea     rcx, [rsp+2C0h+var_246]
0x14001537f  sub     ecx, r8d
0x140015382  lea     eax, [rcx+2]
0x140015385  cmp     eax, ecx
0x140015387  jb      loc_14001554F
0x14001538d  mov     r10d, ecx
0x140015390  add     rcx, 2
0x140015394  cmp     rcx, rdx
0x140015397  ja      loc_14001554F
0x14001539d  movsxd  rcx, r9d
0x1400153a0  mov     rax, r10
0x1400153a3  sub     rax, rcx
0x1400153a6  inc     r9d
0x1400153a9  mov     al, byte ptr [rsp+rax+2C0h+var_250+1]
0x1400153ad  mov     byte ptr [rsp+rcx+2C0h+var_280], al
0x1400153b1  cmp     r9d, 2
0x1400153b5  jb      short loc_14001539D
0x1400153b7  lea     rax, [rsp+2C0h+Src]
0x1400153bc  movzx   ebx, [rsp+2C0h+var_280]
0x1400153c1  sub     r8d, eax
0x1400153c4  add     r8d, edx
0x1400153c7  cmp     ebx, r8d
0x1400153ca  ja      loc_140015523
0x1400153d0  lea     rax, [rsp+2C0h+Src]
0x1400153d5  mov     r8d, ebx; Size
0x1400153d8  add     rax, rbx
0x1400153db  mov     [rsp+2C0h+var_268], rax
0x1400153e0  mov     r9d, [r14]
0x1400153e3  cmp     r9d, ebx
0x1400153e6  jnb     short loc_140015428
0x1400153e8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400153ef  lea     rax, WPP_GLOBAL_Control
0x1400153f6  cmp     rcx, rax
0x1400153f9  jz      short loc_14001541B
0x1400153fb  mov     eax, [rcx+2Ch]
0x1400153fe  test    al, 1
0x140015400  jz      short loc_14001541B
0x140015402  mov     rcx, [rcx+18h]
0x140015406  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x14001540d  mov     edx, 32h ; '2'
0x140015412  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x140015416  call    WPP_SF_Dd
0x14001541b  mov     [r14], ebx
0x14001541e  mov     ebx, 80000005h
0x140015423  jmp     loc_1400155CE
0x140015428  lea     rdx, [rsp+2C0h+Src]; Src
0x14001542d  mov     [r14], ebx
0x140015430  mov     rcx, r12; void *
0x140015433  call    memmove
0x140015438  xor     r8d, r8d
0x14001543b  lea     rdx, [rsp+2C0h+var_280]
0x140015440  lea     rcx, [rsp+2C0h+var_278]
0x140015445  call    ??$Get@G@TpmBufferAccessor@@QEAAJPEAGPEAX@Z; TpmBufferAccessor::Get<ushort>(ushort *,void *)
0x14001544a  test    eax, eax
0x14001544c  jns     short loc_14001548A
0x14001544e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015455  lea     rax, WPP_GLOBAL_Control
0x14001545c  cmp     rcx, rax
0x14001545f  jz      loc_1400155C9
0x140015465  mov     eax, [rcx+2Ch]
0x140015468  test    al, 1
0x14001546a  jz      loc_1400155C9
0x140015470  mov     edx, 33h ; '3'
0x140015475  mov     rcx, [rcx+18h]
0x140015479  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x140015480  call    WPP_SF_
0x140015485  jmp     loc_1400155C9
0x14001548a  mov     eax, dword ptr [rsp+2C0h+var_278]
0x14001548e  sub     eax, dword ptr [rsp+2C0h+var_268]
0x140015492  add     eax, [rsp+2C0h+var_270]
0x140015496  movzx   ebx, [rsp+2C0h+var_280]
0x14001549b  cmp     ebx, eax
0x14001549d  jbe     short loc_1400154C8
0x14001549f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400154a6  lea     rax, WPP_GLOBAL_Control
0x1400154ad  cmp     rcx, rax
0x1400154b0  jz      loc_1400155C9
0x1400154b6  mov     eax, [rcx+2Ch]
0x1400154b9  test    al, 1
0x1400154bb  jz      loc_1400155C9
0x1400154c1  mov     edx, 34h ; '4'
0x1400154c6  jmp     short loc_140015475
0x1400154c8  mov     r9d, [rsi]
0x1400154cb  cmp     r9d, ebx
0x1400154ce  jnb     short loc_14001550A
0x1400154d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400154d7  lea     rax, WPP_GLOBAL_Control
0x1400154de  cmp     rcx, rax
0x1400154e1  jz      short loc_140015503
0x1400154e3  mov     eax, [rcx+2Ch]
0x1400154e6  test    al, 1
0x1400154e8  jz      short loc_140015503
0x1400154ea  mov     rcx, [rcx+18h]
0x1400154ee  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x1400154f5  mov     edx, 35h ; '5'
0x1400154fa  mov     dword ptr [rsp+2C0h+var_2A0], ebx
0x1400154fe  call    WPP_SF_Dd
0x140015503  mov     [rsi], ebx
0x140015505  jmp     loc_14001541E
0x14001550a  mov     rdx, [rsp+2C0h+var_268]; Src
0x14001550f  mov     r8, rbx; Size
0x140015512  mov     rcx, r15; void *
0x140015515  mov     [rsi], ebx
0x140015517  call    memmove
0x14001551c  xor     ebx, ebx
0x14001551e  jmp     loc_1400155CE
0x140015523  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001552a  lea     rax, WPP_GLOBAL_Control
0x140015531  cmp     rcx, rax
0x140015534  jz      loc_1400155C9
0x14001553a  mov     eax, [rcx+2Ch]
0x14001553d  test    al, 1
0x14001553f  jz      loc_1400155C9
0x140015545  mov     edx, 31h ; '1'
0x14001554a  jmp     loc_140015475
0x14001554f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015556  lea     rax, WPP_GLOBAL_Control
0x14001555d  cmp     rcx, rax
0x140015560  jz      short loc_1400155C9
0x140015562  mov     eax, [rcx+2Ch]
0x140015565  test    al, 1
0x140015567  jz      short loc_1400155C9
0x140015569  mov     edx, 30h ; '0'
0x14001556e  jmp     loc_140015475
0x140015573  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001557a  lea     rax, WPP_GLOBAL_Control
0x140015581  cmp     rcx, rax
0x140015584  jz      short loc_1400155C9
0x140015586  mov     eax, [rcx+2Ch]
0x140015589  test    al, 1
0x14001558b  jz      short loc_1400155C9
0x14001558d  mov     edx, 2Fh ; '/'
0x140015592  jmp     loc_140015475
0x140015597  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001559e  lea     rax, WPP_GLOBAL_Control
0x1400155a5  cmp     rcx, rax
0x1400155a8  jz      short loc_1400155C9
0x1400155aa  mov     eax, [rcx+2Ch]
0x1400155ad  test    al, 1
0x1400155af  jz      short loc_1400155C9
0x1400155b1  mov     rcx, [rcx+18h]
0x1400155b5  lea     r8, WPP_d0de2f6a14273316cf6155040bbdf5a0_Traceguids
0x1400155bc  bswap   r9d
0x1400155bf  mov     edx, 2Eh ; '.'
0x1400155c4  call    WPP_SF_d
0x1400155c9  mov     ebx, 0C0000001h
0x1400155ce  mov     eax, ebx
0x1400155d0  mov     rcx, [rbp+1C0h+var_40]
0x1400155d7  xor     rcx, rsp; StackCookie
0x1400155da  call    __security_check_cookie
0x1400155df  add     rsp, 290h
0x1400155e6  pop     r15
0x1400155e8  pop     r14
0x1400155ea  pop     r12
0x1400155ec  pop     rdi
0x1400155ed  pop     rsi
0x1400155ee  pop     rbx
0x1400155ef  pop     rbp
0x1400155f0  retn
```
