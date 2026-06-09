# decoder_context::check_kernel_event(void)

- ea: `0x180058c0c`
- end: `0x18005925a`
- name: `?check_kernel_event@decoder_context@@AEAA_NXZ`
- size: `1614`
- prototype: `char __fastcall(decoder_context *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180059e58`

## callees

- `0x180004510`
- `0x1800048c0`
- `0x1800048e0`
- `0x180004aac`
- `0x180004b14`
- `0x180004c2c`
- `0x1800054d8`
- `0x180005508`
- `0x180044a38`
- `0x180053850`
- `0x18005727c`
- `0x18005735c`
- `0x1800575b0`
- `0x180058c0c`

## string_xrefs

- `0x180058e96`: `StackKeyDelete`
- `0x180058f20`: `ReadyThread`
- `0x180058fca`: `ThreadedDpc`
- `0x180059009`: `MsiInterrupt`
- `0x180059041`: `PmcConfig`

## pseudocode

```c
char __fastcall decoder_context::check_kernel_event(decoder_context *this)
{
  unsigned __int64 v2; // rsi
  __int64 v3; // r13
  char *v4; // rbx
  char *v5; // rdi
  char *v6; // r15
  __int64 *v7; // rcx
  __int64 *v8; // rax
  __int64 *v9; // rdi
  _WORD *v10; // r9
  char **v11; // rcx
  char *v12; // r15
  _WORD **v13; // rcx
  _WORD *v14; // rbx
  __int64 v16; // rcx
  void *v17; // rcx
  _QWORD *v18; // rbx
  void *v19; // rcx
  void *v20; // rcx
  _QWORD *v21; // rbx
  void *v22; // rcx
  void *v23; // rcx
  _QWORD *v24; // rbx
  void *v25; // rcx
  void *v26; // rcx
  _QWORD *v27; // rbx
  void *v28; // rcx
  char *v29; // [rsp+20h] [rbp-E0h] BYREF
  char *v30; // [rsp+28h] [rbp-D8h]
  void *v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *v33[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v35; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v36; // [rsp+78h] [rbp-88h]
  void (__fastcall *v37)(decoder_context *__hidden, struct etw_event *); // [rsp+80h] [rbp-80h]
  char v38; // [rsp+88h] [rbp-78h] BYREF
  const wchar_t *v39; // [rsp+90h] [rbp-70h]
  void (__fastcall *v40)(decoder_context *__hidden, struct etw_event *); // [rsp+98h] [rbp-68h]
  char v41; // [rsp+A0h] [rbp-60h]
  const wchar_t *v42; // [rsp+A8h] [rbp-58h]
  void (__fastcall *v43)(decoder_context *__hidden, struct etw_event *); // [rsp+B0h] [rbp-50h]
  char v44; // [rsp+B8h] [rbp-48h] BYREF
  char v45; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v46; // [rsp+C8h] [rbp-38h]
  void (__fastcall *v47)(decoder_context *__hidden, struct etw_event *); // [rsp+D0h] [rbp-30h]
  char v48; // [rsp+D8h] [rbp-28h]
  const wchar_t *v49; // [rsp+E0h] [rbp-20h]
  void (__fastcall *v50)(decoder_context *__hidden, struct etw_event *); // [rsp+E8h] [rbp-18h]
  char v51; // [rsp+F0h] [rbp-10h]
  const wchar_t *v52; // [rsp+F8h] [rbp-8h]
  void (__fastcall *v53)(decoder_context *__hidden, struct etw_event *); // [rsp+100h] [rbp+0h]
  char v54; // [rsp+108h] [rbp+8h]
  const wchar_t *v55; // [rsp+110h] [rbp+10h]
  void (__fastcall *v56)(decoder_context *__hidden, struct etw_event *); // [rsp+118h] [rbp+18h]
  char v57; // [rsp+120h] [rbp+20h]
  const wchar_t *v58; // [rsp+128h] [rbp+28h]
  void (__fastcall *v59)(decoder_context *__hidden, struct etw_event *); // [rsp+130h] [rbp+30h]
  char v60; // [rsp+138h] [rbp+38h] BYREF
  char v61; // [rsp+140h] [rbp+40h] BYREF
  const wchar_t *v62; // [rsp+148h] [rbp+48h]
  void (__fastcall *v63)(decoder_context *__hidden, struct etw_event *); // [rsp+150h] [rbp+50h]
  char v64; // [rsp+158h] [rbp+58h]
  const wchar_t *v65; // [rsp+160h] [rbp+60h]
  void (__fastcall *v66)(decoder_context *__hidden, struct etw_event *); // [rsp+168h] [rbp+68h]
  char v67; // [rsp+170h] [rbp+70h]
  const wchar_t *v68; // [rsp+178h] [rbp+78h]
  void (__fastcall *v69)(decoder_context *__hidden, struct etw_event *); // [rsp+180h] [rbp+80h]
  char v70; // [rsp+188h] [rbp+88h]
  const wchar_t *v71; // [rsp+190h] [rbp+90h]
  void (__fastcall *v72)(decoder_context *__hidden, struct etw_event *); // [rsp+198h] [rbp+98h]
  char v73; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v74; // [rsp+1A8h] [rbp+A8h]
  void (__fastcall *v75)(decoder_context *__hidden, struct etw_event *); // [rsp+1B0h] [rbp+B0h]
  char v76; // [rsp+1B8h] [rbp+B8h]
  const wchar_t *v77; // [rsp+1C0h] [rbp+C0h]
  void (__fastcall *v78)(decoder_context *__hidden, struct etw_event *); // [rsp+1C8h] [rbp+C8h]
  char v79; // [rsp+1D0h] [rbp+D0h]
  const wchar_t *v80; // [rsp+1D8h] [rbp+D8h]
  void (__fastcall *v81)(decoder_context *__hidden, struct etw_event *); // [rsp+1E0h] [rbp+E0h]
  char v82; // [rsp+1E8h] [rbp+E8h]
  const wchar_t *v83; // [rsp+1F0h] [rbp+F0h]
  void (__fastcall *v84)(decoder_context *__hidden, struct etw_event *); // [rsp+1F8h] [rbp+F8h]
  __int128 v85; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v86[16]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v87; // [rsp+220h] [rbp+120h]
  _BYTE v88[16]; // [rsp+230h] [rbp+130h] BYREF
  __int128 v89; // [rsp+240h] [rbp+140h]
  _BYTE v90[16]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v91; // [rsp+260h] [rbp+160h]
  _BYTE v92[16]; // [rsp+270h] [rbp+170h] BYREF
  __int64 v93; // [rsp+280h] [rbp+180h] BYREF

  v2 = -1;
  if ( dword_1800BED24 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800BED24);
    if ( dword_1800BED24 == -1 )
    {
      v45 = 32;
      v46 = L"Stack";
      v47 = decoder_context::kernel_stackwalk_event;
      v48 = 37;
      v49 = L"StackKeyKernel";
      v50 = decoder_context::kernel_stackwalk_key_event;
      v51 = 38;
      v52 = L"StackKeyUser";
      v53 = decoder_context::kernel_stackwalk_key_event;
      v54 = 35;
      v55 = L"StackKeyDelete";
      v56 = decoder_context::kernel_stackwalk_keystack_event;
      v57 = 36;
      v58 = L"StackKeyRundown";
      v59 = decoder_context::kernel_stackwalk_keystack_event;
      v29 = &v45;
      v30 = &v60;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        Block,
        &v29);
      v85 = StackWalkGuid;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v86,
        Block);
      v38 = 36;
      v39 = L"CSwitch";
      v40 = decoder_context::kernel_cswitch_event;
      v41 = 50;
      v42 = L"ReadyThread";
      v43 = decoder_context::kernel_readythread_event;
      v29 = &v38;
      v30 = &v44;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v33,
        &v29);
      v87 = ThreadGuid;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v88,
        v33);
      v61 = 46;
      v62 = L"SProfile";
      v63 = decoder_context::kernel_sampledprofile_event;
      v64 = 68;
      v65 = L"Dpc";
      v66 = decoder_context::kernel_dpc_event;
      v67 = 69;
      v68 = L"TimerDpc";
      v69 = decoder_context::kernel_dpc_event;
      v70 = 66;
      v71 = L"ThreadedDpc";
      v72 = decoder_context::kernel_dpc_event;
      v73 = 67;
      v74 = L"Interrupt";
      v75 = decoder_context::kernel_interrupt_event;
      v76 = 50;
      v77 = L"MsiInterrupt";
      v78 = decoder_context::kernel_interrupt_event;
      v79 = 95;
      v80 = L"PsvInterrupt";
      v81 = decoder_context::kernel_interrupt_event;
      v82 = 48;
      v83 = L"PmcConfig";
      v84 = decoder_context::kernel_pmcconfig_event;
      v29 = &v61;
      v30 = (char *)&v85;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v32,
        &v29);
      v89 = PerfinfoGuid;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v90,
        v32);
      v35 = 32;
      v36 = L"HardFault";
      v37 = decoder_context::kernel_hardfault_event;
      v29 = &v35;
      v30 = &v38;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v31,
        &v29);
      v91 = PageFaultGuid;
      std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>(
        v92,
        v31);
      v29 = (char *)&v85;
      v30 = (char *)&v93;
      std::map<_GUID,std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>::map<_GUID,std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>(
        v16,
        &v29);
      `eh vector destructor iterator'(
        &v85,
        0x20u,
        4u,
        std::pair<_GUID const,std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>::~pair<_GUID const,std::map<unsigned char,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>);
      v17 = v31[0];
      v18 = (_QWORD *)*((_QWORD *)v31[0] + 1);
      if ( !*((_BYTE *)v18 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>,void *>>>(
            v31,
            v31,
            v18[2]);
          v19 = v18;
          v18 = (_QWORD *)*v18;
          operator delete(v19);
        }
        while ( !*((_BYTE *)v18 + 25) );
        v17 = v31[0];
      }
      operator delete(v17);
      v20 = v32[0];
      v21 = (_QWORD *)*((_QWORD *)v32[0] + 1);
      if ( !*((_BYTE *)v21 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>,void *>>>(
            v32,
            v32,
            v21[2]);
          v22 = v21;
          v21 = (_QWORD *)*v21;
          operator delete(v22);
        }
        while ( !*((_BYTE *)v21 + 25) );
        v20 = v32[0];
      }
      operator delete(v20);
      v23 = v33[0];
      v24 = (_QWORD *)*((_QWORD *)v33[0] + 1);
      if ( !*((_BYTE *)v24 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>,void *>>>(
            v33,
            v33,
            v24[2]);
          v25 = v24;
          v24 = (_QWORD *)*v24;
          operator delete(v25);
        }
        while ( !*((_BYTE *)v24 + 25) );
        v23 = v33[0];
      }
      operator delete(v23);
      v26 = Block[0];
      v27 = (_QWORD *)*((_QWORD *)Block[0] + 1);
      if ( !*((_BYTE *)v27 + 25) )
      {
        do
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned char const,std::pair<unsigned short const *,void (decoder_context::*)(etw_event &)const>>,void *>>>(
            Block,
            Block,
            v27[2]);
          v28 = v27;
          v27 = (_QWORD *)*v27;
          operator delete(v28);
        }
        while ( !*((_BYTE *)v27 + 25) );
        v26 = Block[0];
      }
      operator delete(v26);
      atexit(decoder_context::check_kernel_event_::_2_::_dynamic_atexit_destructor_for__kernel_events__);
      Init_thread_footer(&dword_1800BED24);
    }
  }
  v3 = *((_QWORD *)this + 2);
  v4 = (char *)qword_1800BED28;
  v5 = (char *)*((_QWORD *)qword_1800BED28 + 1);
  v6 = (char *)qword_1800BED28;
  while ( !v5[25] )
  {
    if ( memcmp_0(v5 + 32, (const void *)(v3 + 24), 0x10u) >= 0 )
    {
      v6 = v5;
      v5 = *(char **)v5;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v5 + 2);
    }
  }
  if ( v6[25] || memcmp_0((const void *)(v3 + 24), v6 + 32, 0x10u) < 0 || v6 == v4 )
    return 0;
  v7 = (__int64 *)*((_QWORD *)v6 + 6);
  v8 = (__int64 *)v7[1];
  v9 = v7;
  while ( !*((_BYTE *)v8 + 25) )
  {
    if ( *((_BYTE *)v8 + 32) >= *(_BYTE *)(v3 + 45) )
    {
      v9 = v8;
      v8 = (__int64 *)*v8;
    }
    else
    {
      v8 = (__int64 *)v8[2];
    }
  }
  if ( *((_BYTE *)v9 + 25) || *(_BYTE *)(v3 + 45) < *((_BYTE *)v9 + 32) || v9 == v7 )
    return 0;
  v10 = (_WORD *)v9[5];
  v11 = (char **)((char *)this + 80);
  do
    ++v2;
  while ( v10[v2] );
  if ( v2 > *((_QWORD *)this + 13) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v11, v2);
  }
  else
  {
    if ( *((_QWORD *)this + 13) <= 7u )
      v12 = (char *)this + 80;
    else
      v12 = *v11;
    *((_QWORD *)this + 12) = v2;
    memmove_0(v12, v10, 2 * v2);
    *(_WORD *)&v12[2 * v2] = 0;
  }
  *((_QWORD *)this + 15) = v9[6];
  *((_BYTE *)this + 128) = 1;
  *(_DWORD *)((char *)this + 129) = *(_DWORD *)((char *)&v30 + 1);
  *(_WORD *)((char *)this + 133) = *(_WORD *)((char *)&v30 + 5);
  *((_BYTE *)this + 135) = HIBYTE(v30);
  v13 = (_WORD **)((char *)this + 48);
  if ( *((_QWORD *)this + 9) < 0x10u )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v13, 16);
  }
  else
  {
    v14 = *v13;
    *((_QWORD *)this + 8) = 16;
    memmove_0(v14, L"MSNT_SystemTrace", 0x20u);
    v14[16] = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180058c0c  push    rbp
0x180058c0e  push    rbx
0x180058c0f  push    rsi
0x180058c10  push    rdi
0x180058c11  push    r12
0x180058c13  push    r13
0x180058c15  push    r14
0x180058c17  push    r15
0x180058c19  lea     rbp, [rsp-198h]
0x180058c21  sub     rsp, 298h
0x180058c28  mov     rax, cs:__security_cookie
0x180058c2f  xor     rax, rsp
0x180058c32  mov     [rbp+1D0h+var_50], rax
0x180058c39  mov     r14, rcx
0x180058c3c  mov     edx, cs:_tls_index
0x180058c42  mov     rax, gs:58h
0x180058c4b  mov     ecx, 4
0x180058c50  mov     rax, [rax+rdx*8]
0x180058c54  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180058c58  xor     edi, edi
0x180058c5a  mov     eax, [rcx+rax]
0x180058c5d  cmp     cs:dword_1800BED24, eax
0x180058c63  jg      loc_180058E33
0x180058c69  mov     r13, [r14+10h]
0x180058c6d  mov     rbx, cs:qword_1800BED28
0x180058c74  mov     rdi, [rbx+8]
0x180058c78  xor     eax, eax
0x180058c7a  mov     r15, rbx
0x180058c7d  cmp     [rdi+19h], al
0x180058c80  jnz     short loc_180058CAB
0x180058c82  lea     rcx, [rdi+20h]; Buf1
0x180058c86  mov     r8d, 10h; Size
0x180058c8c  lea     rdx, [r13+18h]; Buf2
0x180058c90  call    memcmp_0
0x180058c95  test    eax, eax
0x180058c97  jns     short loc_180058C9F
0x180058c99  mov     rdi, [rdi+10h]
0x180058c9d  jmp     short loc_180058CA5
0x180058c9f  mov     r15, rdi
0x180058ca2  mov     rdi, [rdi]
0x180058ca5  cmp     byte ptr [rdi+19h], 0
0x180058ca9  jz      short loc_180058C82
0x180058cab  cmp     byte ptr [r15+19h], 0
0x180058cb0  jnz     loc_180058DE8
0x180058cb6  lea     rdx, [r15+20h]; Buf2
0x180058cba  mov     r8d, 10h; Size
0x180058cc0  lea     rcx, [r13+18h]; Buf1
0x180058cc4  call    memcmp_0
0x180058cc9  xor     r12d, r12d
0x180058ccc  test    eax, eax
0x180058cce  js      loc_180058DE8
0x180058cd4  cmp     r15, rbx
0x180058cd7  jz      loc_180058DE8
0x180058cdd  mov     rcx, [r15+30h]
0x180058ce1  mov     rax, [rcx+8]
0x180058ce5  mov     rdi, rcx
0x180058ce8  cmp     [rax+19h], r12b
0x180058cec  jnz     short loc_180058D09
0x180058cee  mov     dl, [r13+2Dh]
0x180058cf2  cmp     [rax+20h], dl
0x180058cf5  jnb     short loc_180058CFD
0x180058cf7  mov     rax, [rax+10h]
0x180058cfb  jmp     short loc_180058D03
0x180058cfd  mov     rdi, rax
0x180058d00  mov     rax, [rax]
0x180058d03  cmp     [rax+19h], r12b
0x180058d07  jz      short loc_180058CF2
0x180058d09  cmp     [rdi+19h], r12b
0x180058d0d  jnz     loc_180058DE8
0x180058d13  mov     al, [rdi+20h]
0x180058d16  cmp     [r13+2Dh], al
0x180058d1a  jb      loc_180058DE8
0x180058d20  cmp     rdi, rcx
0x180058d23  jz      loc_180058DE8
0x180058d29  mov     r9, [rdi+28h]
0x180058d2d  lea     rcx, [r14+50h]
0x180058d31  inc     rsi
0x180058d34  cmp     [r9+rsi*2], r12w
0x180058d39  jnz     short loc_180058D31
0x180058d3b  cmp     rsi, [rcx+18h]
0x180058d3f  ja      short loc_180058D6D
0x180058d41  cmp     qword ptr [rcx+18h], 7
0x180058d46  jbe     short loc_180058D4D
0x180058d48  mov     r15, [rcx]
0x180058d4b  jmp     short loc_180058D50
0x180058d4d  mov     r15, rcx
0x180058d50  mov     [rcx+10h], rsi
0x180058d54  lea     rbx, [rsi+rsi]
0x180058d58  mov     r8, rbx; Size
0x180058d5b  mov     rdx, r9; Src
0x180058d5e  mov     rcx, r15; void *
0x180058d61  call    memmove_0
0x180058d66  mov     [rbx+r15], r12w
0x180058d6b  jmp     short loc_180058D75
0x180058d6d  mov     rdx, rsi
0x180058d70  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180058d75  mov     rax, [rdi+30h]
0x180058d79  mov     [r14+78h], rax
0x180058d7d  mov     byte ptr [r14+80h], 1
0x180058d85  mov     eax, [rsp+2D0h+var_2A7]
0x180058d89  mov     [r14+81h], eax
0x180058d90  movzx   eax, [rsp+2D0h+var_2A3]
0x180058d95  mov     [r14+85h], ax
0x180058d9d  mov     al, [rsp+2D0h+var_2A1]
0x180058da1  mov     [r14+87h], al
0x180058da8  lea     rcx, [r14+30h]
0x180058dac  mov     edx, 10h
0x180058db1  cmp     [rcx+18h], rdx
0x180058db5  jb      short loc_180058DD8
0x180058db7  mov     rbx, [rcx]
0x180058dba  mov     [rcx+10h], rdx
0x180058dbe  lea     r8d, [rdx+10h]; Size
0x180058dc2  lea     rdx, aMsntSystemtrac; "MSNT_SystemTrace"
0x180058dc9  mov     rcx, rbx; void *
0x180058dcc  call    memmove_0
0x180058dd1  mov     [rbx+20h], r12w
0x180058dd6  jmp     short loc_180058DE4
0x180058dd8  lea     r9, aMsntSystemtrac; "MSNT_SystemTrace"
0x180058ddf  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180058de4  mov     al, 1
0x180058de6  jmp     short loc_180058DEA
0x180058de8  xor     al, al
0x180058dea  mov     rcx, [rbp+1D0h+var_50]
0x180058df1  xor     rcx, rsp; StackCookie
0x180058df4  call    __security_check_cookie
0x180058df9  add     rsp, 298h
0x180058e00  pop     r15
0x180058e02  pop     r14
0x180058e04  pop     r13
0x180058e06  pop     r12
0x180058e08  pop     rdi
0x180058e09  pop     rsi
0x180058e0a  pop     rbx
0x180058e0b  pop     rbp
0x180058e0c  retn
0x180058e0d  mov     rdx, r15
0x180058e10  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180058e15  lea     rcx, _decoder_context__check_kernel_event____2____dynamic_atexit_destructor_for__kernel_events__; void (__cdecl *)()
0x180058e1c  call    atexit
0x180058e21  nop
0x180058e22  lea     rcx, dword_1800BED24
0x180058e29  call    _Init_thread_footer
0x180058e2e  jmp     loc_180058C69
0x180058e33  lea     rcx, dword_1800BED24
0x180058e3a  call    _Init_thread_header
0x180058e3f  cmp     cs:dword_1800BED24, esi
0x180058e45  jnz     loc_180058C69
0x180058e4b  mov     [rbp+1D0h+var_210], 20h ; ' '
0x180058e4f  lea     rax, aStack_0; "Stack"
0x180058e56  mov     [rbp+1D0h+var_208], rax
0x180058e5a  lea     rax, ?kernel_stackwalk_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_stackwalk_event(etw_event &)
0x180058e61  mov     [rbp+1D0h+var_200], rax
0x180058e65  mov     [rbp+1D0h+var_1F8], 25h ; '%'
0x180058e69  lea     rax, aStackkeykernel; "StackKeyKernel"
0x180058e70  mov     [rbp+1D0h+var_1F0], rax
0x180058e74  lea     rcx, ?kernel_stackwalk_key_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_stackwalk_key_event(etw_event &)
0x180058e7b  mov     [rbp+1D0h+var_1E8], rcx
0x180058e7f  mov     [rbp+1D0h+var_1E0], 26h ; '&'
0x180058e83  lea     rax, aStackkeyuser; "StackKeyUser"
0x180058e8a  mov     [rbp+1D0h+var_1D8], rax
0x180058e8e  mov     [rbp+1D0h+var_1D0], rcx
0x180058e92  mov     [rbp+1D0h+var_1C8], 23h ; '#'
0x180058e96  lea     rax, aStackkeydelete; "StackKeyDelete"
0x180058e9d  mov     [rbp+1D0h+var_1C0], rax
0x180058ea1  lea     rcx, ?kernel_stackwalk_keystack_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_stackwalk_keystack_event(etw_event &)
0x180058ea8  mov     [rbp+1D0h+var_1B8], rcx
0x180058eac  mov     [rbp+1D0h+var_1B0], 24h ; '$'
0x180058eb0  lea     rax, aStackkeyrundow; "StackKeyRundown"
0x180058eb7  mov     [rbp+1D0h+var_1A8], rax
0x180058ebb  mov     [rbp+1D0h+var_1A0], rcx
0x180058ebf  lea     rax, [rbp+1D0h+var_210]
0x180058ec3  mov     [rsp+2D0h+var_2B0], rax
0x180058ec8  lea     rax, [rbp+1D0h+var_198]
0x180058ecc  mov     [rsp+28h], rax
0x180058ed1  lea     rdx, [rsp+2D0h+var_2B0]
0x180058ed6  lea     rcx, [rsp+2D0h+Block]
0x180058edb  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@1@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::initializer_list<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>)
0x180058ee0  nop
0x180058ee1  movups  xmm0, cs:StackWalkGuid
0x180058ee8  movdqu  [rbp+1D0h+var_D0], xmm0
0x180058ef0  lea     rdx, [rsp+2D0h+Block]
0x180058ef5  lea     rcx, [rbp+1D0h+var_C0]
0x180058efc  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>> const &)
0x180058f01  nop
0x180058f02  mov     [rbp+1D0h+var_248], 24h ; '$'
0x180058f06  lea     rax, aCswitch; "CSwitch"
0x180058f0d  mov     [rbp+1D0h+var_240], rax
0x180058f11  lea     rax, ?kernel_cswitch_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_cswitch_event(etw_event &)
0x180058f18  mov     [rbp+1D0h+var_238], rax
0x180058f1c  mov     [rbp+1D0h+var_230], 32h ; '2'
0x180058f20  lea     rax, aReadythread; "ReadyThread"
0x180058f27  mov     [rbp+1D0h+var_228], rax
0x180058f2b  lea     rax, ?kernel_readythread_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_readythread_event(etw_event &)
0x180058f32  mov     [rbp+1D0h+var_220], rax
0x180058f36  lea     rax, [rbp+1D0h+var_248]
0x180058f3a  mov     [rsp+2D0h+var_2B0], rax
0x180058f3f  lea     rax, [rbp+1D0h+var_218]
0x180058f43  mov     [rsp+28h], rax
0x180058f48  lea     rdx, [rsp+2D0h+var_2B0]
0x180058f4d  lea     rcx, [rsp+2D0h+var_280]
0x180058f52  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@1@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::initializer_list<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>)
0x180058f57  nop
0x180058f58  movups  xmm0, cs:ThreadGuid
0x180058f5f  movdqu  [rbp+1D0h+var_B0], xmm0
0x180058f67  lea     rdx, [rsp+2D0h+var_280]
0x180058f6c  lea     rcx, [rbp+1D0h+var_A0]
0x180058f73  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>> const &)
0x180058f78  nop
0x180058f79  mov     [rbp+1D0h+var_190], 2Eh ; '.'
0x180058f7d  lea     rax, aSprofile; "SProfile"
0x180058f84  mov     [rbp+1D0h+var_188], rax
0x180058f88  lea     rax, ?kernel_sampledprofile_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_sampledprofile_event(etw_event &)
0x180058f8f  mov     [rbp+1D0h+var_180], rax
0x180058f93  mov     [rbp+1D0h+var_178], 44h ; 'D'
0x180058f97  lea     rax, aDpc; "Dpc"
0x180058f9e  mov     [rbp+1D0h+var_170], rax
0x180058fa2  lea     rcx, ?kernel_dpc_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_dpc_event(etw_event &)
0x180058fa9  mov     [rbp+1D0h+var_168], rcx
0x180058fad  mov     [rbp+1D0h+var_160], 45h ; 'E'
0x180058fb1  lea     rax, aTimerdpc; "TimerDpc"
0x180058fb8  mov     [rbp+1D0h+var_158], rax
0x180058fbc  mov     [rbp+1D0h+var_150], rcx
0x180058fc3  mov     [rbp+1D0h+var_148], 42h ; 'B'
0x180058fca  lea     rax, aThreadeddpc; "ThreadedDpc"
0x180058fd1  mov     [rbp+1D0h+var_140], rax
0x180058fd8  mov     [rbp+1D0h+var_138], rcx
0x180058fdf  mov     [rbp+1D0h+var_130], 43h ; 'C'
0x180058fe6  lea     rax, aInterrupt; "Interrupt"
0x180058fed  mov     [rbp+1D0h+var_128], rax
0x180058ff4  lea     rcx, ?kernel_interrupt_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_interrupt_event(etw_event &)
0x180058ffb  mov     [rbp+1D0h+var_120], rcx
0x180059002  mov     [rbp+1D0h+var_118], 32h ; '2'
0x180059009  lea     rax, aMsiinterrupt; "MsiInterrupt"
0x180059010  mov     [rbp+1D0h+var_110], rax
0x180059017  mov     [rbp+1D0h+var_108], rcx
0x18005901e  mov     [rbp+1D0h+var_100], 5Fh ; '_'
0x180059025  lea     rax, aPsvinterrupt; "PsvInterrupt"
0x18005902c  mov     [rbp+1D0h+var_F8], rax
0x180059033  mov     [rbp+1D0h+var_F0], rcx
0x18005903a  mov     [rbp+1D0h+var_E8], 30h ; '0'
0x180059041  lea     rax, aPmcconfig; "PmcConfig"
0x180059048  mov     [rbp+1D0h+var_E0], rax
0x18005904f  lea     rax, ?kernel_pmcconfig_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_pmcconfig_event(etw_event &)
0x180059056  mov     [rbp+1D0h+var_D8], rax
0x18005905d  lea     rax, [rbp+1D0h+var_190]
0x180059061  mov     [rsp+2D0h+var_2B0], rax
0x180059066  lea     rax, [rbp+1D0h+var_D0]
0x18005906d  mov     [rsp+28h], rax
0x180059072  lea     rdx, [rsp+2D0h+var_2B0]
0x180059077  lea     rcx, [rsp+2D0h+var_290]
0x18005907c  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@1@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::initializer_list<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>)
0x180059081  nop
0x180059082  movups  xmm0, cs:PerfinfoGuid
0x180059089  movdqu  [rbp+1D0h+var_90], xmm0
0x180059091  lea     rdx, [rsp+2D0h+var_290]
0x180059096  lea     rcx, [rbp+1D0h+var_80]
0x18005909d  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>> const &)
0x1800590a2  nop
0x1800590a3  mov     [rsp+2D0h+var_260], 20h ; ' '
0x1800590a8  lea     rax, aHardfault; "HardFault"
0x1800590af  mov     [rsp+2D0h+var_258], rax
0x1800590b4  lea     rax, ?kernel_hardfault_event@decoder_context@@AEBAXAEAUetw_event@@@Z; decoder_context::kernel_hardfault_event(etw_event &)
0x1800590bb  mov     [rbp+1D0h+var_250], rax
0x1800590bf  lea     rax, [rsp+2D0h+var_260]
0x1800590c4  mov     [rsp+2D0h+var_2B0], rax
0x1800590c9  lea     rax, [rbp+1D0h+var_248]
0x1800590cd  mov     [rsp+28h], rax
0x1800590d2  lea     rdx, [rsp+2D0h+var_2B0]
0x1800590d7  lea     rcx, [rsp+2D0h+var_2A0]
0x1800590dc  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@1@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::initializer_list<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>)
0x1800590e1  nop
0x1800590e2  movups  xmm0, cs:PageFaultGuid
0x1800590e9  movdqu  [rbp+1D0h+var_70], xmm0
0x1800590f1  lea     rdx, [rsp+2D0h+var_2A0]
0x1800590f6  lea     rcx, [rbp+1D0h+var_60]
0x1800590fd  call    ??0?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>(std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>> const &)
0x180059102  nop
0x180059103  lea     rax, [rbp+1D0h+var_D0]
0x18005910a  mov     [rsp+2D0h+var_2B0], rax
0x18005910f  lea     rax, [rbp+1D0h+var_50]
0x180059116  mov     [rsp+28h], rax
0x18005911b  lea     rdx, [rsp+2D0h+var_2B0]
0x180059120  call    ??0?$map@U_GUID@@V?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@@std@@@3@@std@@QEAA@V?$initializer_list@U?$pair@$$CBU_GUID@@V?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@@std@@@1@@Z; std::map<_GUID,std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>::map<_GUID,std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>(std::initializer_list<std::pair<_GUID const,std::map<uchar,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>>)
0x180059125  nop
0x180059126  lea     r9, ??1?$pair@$$CBU_GUID@@V?$map@EU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@U?$less@E@2@V?$allocator@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@2@@std@@@std@@QEAA@XZ; void (*)(void *)
0x18005912d  mov     edx, 20h ; ' '; unsigned __int64
0x180059132  lea     r8d, [rdx-1Ch]; unsigned __int64
0x180059136  lea     rcx, [rbp+1D0h+var_D0]; void *
0x18005913d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180059142  nop
0x180059143  mov     rcx, [rsp+2D0h+var_2A0]
0x180059148  mov     rbx, [rcx+8]
0x18005914c  mov     r15d, 38h ; '8'
0x180059152  cmp     [rbx+19h], dil
0x180059156  jnz     short loc_180059184
0x180059158  mov     r8, [rbx+10h]
0x18005915c  lea     rdx, [rsp+2D0h+var_2A0]
0x180059161  lea     rcx, [rsp+2D0h+var_2A0]
0x180059166  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBEU?$pair@PEBGP8decoder_context@@EBAXAEAUetw_event@@@Z@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>,void *>>>(std::allocator<std::_Tree_node<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>,void *>> &,std::_Tree_node<std::pair<uchar const,std::pair<ushort const *,void (decoder_context::*)(etw_event &)>>,void *> *)
0x18005916b  mov     rcx, rbx; Block
  ... truncated ...
```
