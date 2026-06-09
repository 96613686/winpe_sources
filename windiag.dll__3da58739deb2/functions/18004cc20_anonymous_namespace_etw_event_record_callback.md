# _anonymous_namespace_::etw_event_record_callback

- ea: `0x18004cc20`
- end: `0x18004d11b`
- name: `_anonymous_namespace_::etw_event_record_callback`
- size: `1275`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180004510`
- `0x18000491c`
- `0x18003a52c`
- `0x18003b0bc`
- `0x18003f6b8`
- `0x180041564`
- `0x180045744`
- `0x180047150`
- `0x18004760c`
- `0x180048fd8`
- `0x18004a490`
- `0x18004b24c`
- `0x18004b324`
- `0x18004bfb8`
- `0x18004cc20`
- `0x18005134c`
- `0x180059e58`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18004ccce`
- `msvcp_win!_Mtx_unlock` at `0x18004ccce`
- `msvcp_win!_Mtx_lock` at `0x18004cc83`
- `msvcp_win!_Mtx_lock` at `0x18004cc83`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004cc92`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004ccad`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004cc92`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18004ccad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cc64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004cc64`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall anonymous_namespace_::etw_event_record_callback(__int64 a1)
{
  __int64 v2; // rdi
  int v3; // ebx
  __int64 v4; // rax
  _Mtx_t v5; // rbx
  int v6; // eax
  char v7; // r14
  __int64 v8; // rcx
  _WORD *v9; // rcx
  _WORD *v10; // rcx
  char v11; // r14
  __int64 v12; // r9
  char v13; // bl
  __int16 v14; // r14
  _QWORD *v15; // rax
  unsigned __int64 v16; // rdx
  unsigned __int16 v17; // ax
  __int64 v18; // rsi
  __m128i si128; // xmm6
  __int64 v20; // rbx
  __int64 v21; // rax
  __int64 v22; // rbx
  struct _Mtx_internal_imp_t *v23; // rbx
  char v25; // [rsp+20h] [rbp-1E8h]
  _BYTE v26[168]; // [rsp+28h] [rbp-1E0h] BYREF
  __int128 v27; // [rsp+D0h] [rbp-138h] BYREF
  __m128i v28; // [rsp+E0h] [rbp-128h] BYREF
  __int128 v29; // [rsp+F0h] [rbp-118h] BYREF
  __int128 v30; // [rsp+100h] [rbp-108h]
  _OWORD v31[5]; // [rsp+110h] [rbp-F8h] BYREF
  __int16 v32; // [rsp+160h] [rbp-A8h]
  int v33; // [rsp+162h] [rbp-A6h]
  __int16 v34; // [rsp+166h] [rbp-A2h]
  _BYTE v35[32]; // [rsp+168h] [rbp-A0h] BYREF
  _BYTE v36[32]; // [rsp+188h] [rbp-80h] BYREF
  _QWORD v37[3]; // [rsp+1A8h] [rbp-60h] BYREF

  v2 = *(_QWORD *)(a1 + 104);
  if ( *(_BYTE *)(v2 + 112)
    || (v3 = *(_DWORD *)(a1 + 12), GetCurrentProcessId() != v3)
    || (LOBYTE(v4) = 0, (*(_WORD *)(a1 + 4) & 0x100) != 0) )
  {
    v5 = *(_Mtx_t *)v2;
    v6 = _Mtx_lock(*(_Mtx_t *)v2);
    try
    {
      if ( v6 )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)v5 + 19) == 0x7FFFFFFF )
      {
        *((_DWORD *)v5 + 19) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      if ( *((_BYTE *)v5 + 208) || (v7 = 0, *((_BYTE *)v5 + 209)) )
        v7 = 1;
      LOBYTE(v4) = _Mtx_unlock(v5);
      if ( !v7 )
      {
        *(_QWORD *)(v2 + 16) = a1;
        v8 = *(_QWORD *)(a1 + 96);
        *(_QWORD *)(v2 + 24) = v8;
        *(_QWORD *)(v2 + 32) = v8 + *(unsigned __int16 *)(a1 + 86);
        LOBYTE(v4) = 4;
        if ( (*(_BYTE *)(a1 + 4) & 0x20) == 0 )
          LOBYTE(v4) = 8;
        *(_BYTE *)(v2 + 40) = v4;
        *(_BYTE *)(v2 + 42) = 0;
        *(_BYTE *)(v2 + 128) = 0;
        *(_QWORD *)(v2 + 64) = 0;
        if ( *(_QWORD *)(v2 + 72) <= 7u )
          v9 = (_WORD *)(v2 + 48);
        else
          v9 = *(_WORD **)(v2 + 48);
        *v9 = 0;
        *(_QWORD *)(v2 + 96) = 0;
        if ( *(_QWORD *)(v2 + 104) <= 7u )
          v10 = (_WORD *)(v2 + 80);
        else
          v10 = *(_WORD **)(v2 + 80);
        *v10 = 0;
        if ( *(_BYTE *)(v2 + 264) && *(_QWORD *)(v2 + 16) )
        {
          decoder_context::get_event_info((decoder_context *)v2);
          LOBYTE(v4) = etw_event_summary_t::update(v2 + 272, *(_QWORD *)(v2 + 16), v2 + 80);
          v11 = v4;
          v25 = v4;
        }
        else
        {
          v11 = 0;
          v25 = 0;
        }
        v12 = *(_QWORD *)(v2 + 16);
        if ( !v12
          || (*(_QWORD *)&v27 = v2, *(_BYTE *)(v2 + 456)) && (v4 = *(_QWORD *)(v2 + 448), *(_QWORD *)(v12 + 16) < v4)
          || *(_BYTE *)(v2 + 472) && (v4 = *(_QWORD *)(v2 + 464), *(_QWORD *)(v12 + 16) > v4) )
        {
          v13 = 0;
        }
        else
        {
          LOBYTE(v4) = etw_event_filter_t::check_event_filter<_lambda_214fd932a541399572a50b75d59972f1_>(
                         v2 + 424,
                         v12,
                         &v27);
          v13 = v4;
        }
        if ( v11 || v13 )
        {
          v14 = *(_BYTE *)(a1 + 81) == 8 ? *(unsigned __int8 *)(a1 + 80) : *(_WORD *)(a1 + 80);
          decoder_context::get_event_info((decoder_context *)v2);
          if ( v13 == 2
            || (LOBYTE(v4) = anonymous_namespace_::etw_decode_event((_BYTE *)v2, v14, v25, v13 != 0), !(_BYTE)v4) )
          {
            v31[0] = *(_OWORD *)a1;
            v31[1] = *(_OWORD *)(a1 + 16);
            v31[2] = *(_OWORD *)(a1 + 32);
            v31[3] = *(_OWORD *)(a1 + 48);
            v31[4] = *(_OWORD *)(a1 + 64);
            v32 = v14;
            v33 = 0;
            v34 = 0;
            std::wstring::wstring(v35, v2 + 80);
            std::wstring::wstring(v36, v2 + 48);
            v37[0] = 0;
            v37[1] = 0;
            v15 = operator new(0x70u);
            *v15 = v15;
            v15[1] = v15;
            v15[2] = v15;
            *((_WORD *)v15 + 12) = 257;
            v37[0] = v15;
            v16 = *(_QWORD *)(v2 + 24);
            if ( *(_QWORD *)(v2 + 32) < v16 )
              v17 = 0;
            else
              v17 = *(_WORD *)(v2 + 32) - v16;
            v18 = v17;
            v27 = 0;
            v28 = 0;
            if ( v17 )
            {
              std::string::_Construct<1,char const *>(&v27, v16, v17);
              si128 = _mm_loadu_si128(&v28);
            }
            else
            {
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              v28 = si128;
              LOBYTE(v27) = 0;
            }
            v29 = 0;
            v30 = 0;
            std::string::_Construct<1,char const *>(&v29, "__bytes", 7);
            v20 = std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](
                    v37,
                    &v29);
            if ( *(_BYTE *)(v20 + 40) == 4 )
            {
              std::string::operator=(v20, &v27);
            }
            else
            {
              std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(v20);
              *(_OWORD *)v20 = v27;
              *(__m128i *)(v20 + 16) = si128;
              v28 = _mm_load_si128((const __m128i *)&_xmm);
              LOBYTE(v27) = 0;
              *(_BYTE *)(v20 + 40) = 4;
            }
            std::string::~string(&v29);
            std::string::~string(&v27);
            v29 = 0;
            v30 = 0;
            std::string::_Construct<1,char const *>(&v29, "__length", 8);
            v21 = std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](
                    v37,
                    &v29);
            v22 = v21;
            if ( *(_BYTE *)(v21 + 40) == 1 )
            {
              *(_QWORD *)v21 = v18;
              *(_BYTE *)(v21 + 8) = 0;
              *(_DWORD *)(v21 + 9) = *(_DWORD *)((char *)&v27 + 9);
              *(_WORD *)(v21 + 13) = *(_WORD *)((char *)&v27 + 13);
              *(_BYTE *)(v21 + 15) = HIBYTE(v27);
            }
            else
            {
              std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(v21);
              *(_QWORD *)v22 = v18;
              *(_BYTE *)(v22 + 8) = 0;
              *(_DWORD *)(v22 + 9) = *(_DWORD *)((char *)&v27 + 9);
              *(_WORD *)(v22 + 13) = *(_WORD *)((char *)&v27 + 13);
              *(_BYTE *)(v22 + 15) = HIBYTE(v27);
              *(_BYTE *)(v22 + 40) = 1;
            }
            std::string::~string(&v29);
            v23 = *(struct _Mtx_internal_imp_t **)v2;
            etw_event::etw_event(v26, v31);
            sync_q<etw_event>::add(v23);
            __1___Tree_V___Tmap_traits_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__variant__NUetw_integer__NUetw_pointer__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Uetw_stack__Uetw_stack_user__Uetw_key_stack__V__vector__JV__allocator__J_std___4_V__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__4__2_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2_V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__variant__NUetw_integer__NUetw_pointer__V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Uetw_stack__Uetw_stack_user__Uetw_key_stack__V__vector__JV__allocator__J_std___4_V__vector_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__allocator_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__4__2__std___2__0A__std___std__QEAA_XZ(v37);
            std::wstring::~wstring(v36);
            LOBYTE(v4) = std::wstring::~wstring(v35);
          }
        }
      }
    }
    catch ( std::exception )
    {
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004cc20  mov     rax, rsp
0x18004cc23  mov     [rax+10h], rbx
0x18004cc27  mov     [rax+18h], rsi
0x18004cc2b  push    rdi
0x18004cc2c  push    r12
0x18004cc2e  push    r13
0x18004cc30  push    r14
0x18004cc32  push    r15
0x18004cc34  sub     rsp, 1E0h
0x18004cc3b  movaps  xmmword ptr [rax-38h], xmm6
0x18004cc3f  mov     rax, cs:__security_cookie
0x18004cc46  xor     rax, rsp
0x18004cc49  mov     [rsp+208h+var_48], rax
0x18004cc51  mov     rsi, rcx
0x18004cc54  mov     rdi, [rcx+68h]
0x18004cc58  xor     r13d, r13d
0x18004cc5b  cmp     [rdi+70h], r13b
0x18004cc5f  jnz     short loc_18004CC7D
0x18004cc61  mov     ebx, [rcx+0Ch]
0x18004cc64  call    cs:__imp_GetCurrentProcessId
0x18004cc6a  cmp     eax, ebx
0x18004cc6c  jnz     short loc_18004CC7D
0x18004cc6e  mov     eax, 100h
0x18004cc73  test    [rsi+4], ax
0x18004cc77  jz      loc_18004D0E8
0x18004cc7d  mov     rbx, [rdi]
0x18004cc80  mov     rcx, rbx; _Mtx_t
0x18004cc83  call    cs:__imp__Mtx_lock
0x18004cc89  test    eax, eax
0x18004cc8b  jz      short loc_18004CC98
0x18004cc8d  mov     ecx, 5
0x18004cc92  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004cc98  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004cc9f  jnz     short loc_18004CCB3
0x18004cca1  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18004cca8  mov     ecx, 6
0x18004ccad  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004ccb3  cmp     [rbx+0D0h], r13b
0x18004ccba  jnz     short loc_18004CCC8
0x18004ccbc  cmp     [rbx+0D1h], r13b
0x18004ccc3  mov     r14b, r13b
0x18004ccc6  jz      short loc_18004CCCB
0x18004ccc8  mov     r14b, 1
0x18004cccb  mov     rcx, rbx; _Mtx_t
0x18004ccce  call    cs:__imp__Mtx_unlock
0x18004ccd4  test    r14b, r14b
0x18004ccd7  jnz     loc_18004D0E8
0x18004ccdd  mov     [rdi+10h], rsi
0x18004cce1  mov     rcx, [rsi+60h]
0x18004cce5  mov     [rdi+18h], rcx
0x18004cce9  movzx   eax, word ptr [rsi+56h]
0x18004cced  add     rax, rcx
0x18004ccf0  mov     [rdi+20h], rax
0x18004ccf4  test    byte ptr [rsi+4], 20h
0x18004ccf8  mov     al, 4
0x18004ccfa  jnz     short loc_18004CCFE
0x18004ccfc  mov     al, 8
0x18004ccfe  mov     [rdi+28h], al
0x18004cd01  mov     [rdi+2Ah], r13b
0x18004cd05  mov     [rdi+80h], r13b
0x18004cd0c  lea     r15, [rdi+30h]
0x18004cd10  mov     [r15+10h], r13
0x18004cd14  cmp     qword ptr [r15+18h], 7
0x18004cd19  jbe     short loc_18004CD20
0x18004cd1b  mov     rcx, [r15]
0x18004cd1e  jmp     short loc_18004CD23
0x18004cd20  mov     rcx, r15
0x18004cd23  mov     [rcx], r13w
0x18004cd27  lea     r12, [rdi+50h]
0x18004cd2b  mov     [r12+10h], r13
0x18004cd30  cmp     qword ptr [r12+18h], 7
0x18004cd36  jbe     short loc_18004CD3E
0x18004cd38  mov     rcx, [r12]
0x18004cd3c  jmp     short loc_18004CD41
0x18004cd3e  mov     rcx, r12
0x18004cd41  mov     [rcx], r13w
0x18004cd45  cmp     [rdi+108h], r13b
0x18004cd4c  jz      short loc_18004CD78
0x18004cd4e  cmp     [rdi+10h], r13
0x18004cd52  jz      short loc_18004CD78
0x18004cd54  mov     rcx, rdi; this
0x18004cd57  call    ?get_event_info@decoder_context@@QEAAXXZ; decoder_context::get_event_info(void)
0x18004cd5c  lea     rcx, [rdi+110h]
0x18004cd63  mov     r8, r12
0x18004cd66  mov     rdx, [rdi+10h]
0x18004cd6a  call    ?update@etw_event_summary_t@@QEAA_NAEBU_EVENT_RECORD@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; etw_event_summary_t::update(_EVENT_RECORD const &,std::wstring const &)
0x18004cd6f  mov     r14b, al
0x18004cd72  mov     [rsp+208h+var_1E8], al
0x18004cd76  jmp     short loc_18004CD80
0x18004cd78  mov     r14b, r13b
0x18004cd7b  mov     [rsp+208h+var_1E8], r13b
0x18004cd80  mov     r9, [rdi+10h]
0x18004cd84  test    r9, r9
0x18004cd87  jnz     short loc_18004CD8E
0x18004cd89  mov     bl, r13b
0x18004cd8c  jmp     short loc_18004CDCF
0x18004cd8e  lea     rcx, [rdi+1A8h]
0x18004cd95  mov     qword ptr [rsp+208h+var_138], rdi
0x18004cd9d  cmp     [rcx+20h], r13b
0x18004cda1  jz      short loc_18004CDAD
0x18004cda3  mov     rax, [rcx+18h]
0x18004cda7  cmp     [r9+10h], rax
0x18004cdab  jl      short loc_18004CD89
0x18004cdad  cmp     [rcx+30h], r13b
0x18004cdb1  jz      short loc_18004CDBD
0x18004cdb3  mov     rax, [rcx+28h]
0x18004cdb7  cmp     [r9+10h], rax
0x18004cdbb  jg      short loc_18004CD89
0x18004cdbd  lea     r8, [rsp+208h+var_138]
0x18004cdc5  mov     rdx, r9
0x18004cdc8  call    ??$check_event_filter@V_lambda_214fd932a541399572a50b75d59972f1_@@@etw_event_filter_t@@AEAA?AW4match_result_t@0@AEBU_EVENT_RECORD@@AEBV_lambda_214fd932a541399572a50b75d59972f1_@@@Z; etw_event_filter_t::check_event_filter<_lambda_214fd932a541399572a50b75d59972f1_>(_EVENT_RECORD const &,_lambda_214fd932a541399572a50b75d59972f1_ const &)
0x18004cdcd  mov     bl, al
0x18004cdcf  test    bl, bl
0x18004cdd1  setnz   r13b
0x18004cdd5  test    r14b, r14b
0x18004cdd8  jnz     short loc_18004CDE2
0x18004cdda  test    bl, bl
0x18004cddc  jz      loc_18004D0E8
0x18004cde2  cmp     byte ptr [rsi+51h], 8
0x18004cde6  jnz     short loc_18004CDEF
0x18004cde8  movzx   r14d, byte ptr [rsi+50h]
0x18004cded  jmp     short loc_18004CDF4
0x18004cdef  movzx   r14d, word ptr [rsi+50h]
0x18004cdf4  mov     rcx, rdi; this
0x18004cdf7  call    ?get_event_info@decoder_context@@QEAAXXZ; decoder_context::get_event_info(void)
0x18004cdfc  cmp     bl, 2
0x18004cdff  jz      short loc_18004CE22
0x18004ce01  mov     r9b, r13b
0x18004ce04  mov     r8b, [rsp+208h+var_1E8]
0x18004ce09  movzx   edx, r14w
0x18004ce0d  mov     rcx, rdi
0x18004ce10  call    _anonymous_namespace___etw_decode_event
0x18004ce15  xor     r13d, r13d
0x18004ce18  test    al, al
0x18004ce1a  jnz     loc_18004D0E8
0x18004ce20  jmp     short loc_18004CE25
0x18004ce22  xor     r13d, r13d
0x18004ce25  movups  xmm0, xmmword ptr [rsi]
0x18004ce28  movaps  [rsp+208h+var_F8], xmm0
0x18004ce30  movups  xmm1, xmmword ptr [rsi+10h]
0x18004ce34  movaps  [rsp+208h+var_E8], xmm1
0x18004ce3c  movups  xmm0, xmmword ptr [rsi+20h]
0x18004ce40  movaps  [rsp+208h+var_D8], xmm0
0x18004ce48  movups  xmm1, xmmword ptr [rsi+30h]
0x18004ce4c  movaps  [rsp+208h+var_C8], xmm1
0x18004ce54  movups  xmm0, xmmword ptr [rsi+40h]
0x18004ce58  movaps  [rsp+208h+var_B8], xmm0
0x18004ce60  mov     [rsp+208h+var_A8], r14w
0x18004ce69  xor     eax, eax
0x18004ce6b  mov     [rsp+208h+var_A6], eax
0x18004ce72  mov     [rsp+208h+var_A2], ax
0x18004ce7a  mov     rdx, r12
0x18004ce7d  lea     rcx, [rsp+208h+var_A0]
0x18004ce85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ce8a  nop
0x18004ce8b  mov     rdx, r15
0x18004ce8e  lea     rcx, [rsp+208h+var_80]
0x18004ce96  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ce9b  nop
0x18004ce9c  mov     [rsp+208h+var_60], r13
0x18004cea4  mov     [rsp+208h+var_58], r13
0x18004ceac  mov     ecx, 70h ; 'p'; Size
0x18004ceb1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004ceb6  mov     [rax], rax
0x18004ceb9  mov     [rax+8], rax
0x18004cebd  mov     [rax+10h], rax
0x18004cec1  mov     word ptr [rax+18h], 101h
0x18004cec7  mov     [rsp+208h+var_60], rax
0x18004cecf  mov     rdx, [rdi+18h]
0x18004ced3  cmp     [rdi+20h], rdx
0x18004ced7  jb      short loc_18004CEE2
0x18004ced9  movzx   eax, word ptr [rdi+20h]
0x18004cedd  sub     ax, dx
0x18004cee0  jmp     short loc_18004CEE5
0x18004cee2  mov     eax, r13d
0x18004cee5  movzx   esi, ax
0x18004cee8  xorps   xmm0, xmm0
0x18004ceeb  movups  [rsp+208h+var_138], xmm0
0x18004cef3  xorps   xmm1, xmm1
0x18004cef6  movdqu  [rsp+208h+var_128], xmm1
0x18004ceff  test    rsi, rsi
0x18004cf02  jnz     short loc_18004CF1F
0x18004cf04  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18004cf0c  movdqu  [rsp+208h+var_128], xmm6
0x18004cf15  mov     byte ptr [rsp+208h+var_138], r13b
0x18004cf1d  jmp     short loc_18004CF38
0x18004cf1f  mov     r8, rsi
0x18004cf22  lea     rcx, [rsp+208h+var_138]
0x18004cf2a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004cf2f  movdqu  xmm6, [rsp+208h+var_128]
0x18004cf38  xorps   xmm0, xmm0
0x18004cf3b  movups  [rsp+208h+var_118], xmm0
0x18004cf43  xorps   xmm1, xmm1
0x18004cf46  movdqu  [rsp+208h+var_108], xmm1
0x18004cf4f  mov     r8d, 7
0x18004cf55  lea     rdx, aBytes; "__bytes"
0x18004cf5c  lea     rcx, [rsp+208h+var_118]
0x18004cf64  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004cf69  nop
0x18004cf6a  lea     rdx, [rsp+208h+var_118]
0x18004cf72  lea     rcx, [rsp+208h+var_60]
0x18004cf7a  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@@std@@@2@@std@@QEAAAEAV?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](std::string &&)
0x18004cf7f  mov     rbx, rax
0x18004cf82  mov     rcx, rax
0x18004cf85  cmp     byte ptr [rax+28h], 4
0x18004cf89  jnz     short loc_18004CF9A
0x18004cf8b  lea     rdx, [rsp+208h+var_138]
0x18004cf93  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18004cf98  jmp     short loc_18004CFCB
0x18004cf9a  call    ?_Reset@?$_Variant_base@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@std@@QEAAXXZ; std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(void)
0x18004cf9f  movups  xmm0, [rsp+208h+var_138]
0x18004cfa7  movups  xmmword ptr [rbx], xmm0
0x18004cfaa  movups  xmmword ptr [rbx+10h], xmm6
0x18004cfae  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18004cfb6  movdqu  [rsp+208h+var_128], xmm0
0x18004cfbf  mov     byte ptr [rsp+208h+var_138], r13b
0x18004cfc7  mov     byte ptr [rbx+28h], 4
0x18004cfcb  lea     rcx, [rsp+208h+var_118]
0x18004cfd3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004cfd8  nop
0x18004cfd9  lea     rcx, [rsp+208h+var_138]
0x18004cfe1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004cfe6  xorps   xmm0, xmm0
0x18004cfe9  movups  [rsp+208h+var_118], xmm0
0x18004cff1  xorps   xmm1, xmm1
0x18004cff4  movdqu  [rsp+208h+var_108], xmm1
0x18004cffd  mov     r8d, 8
0x18004d003  lea     rdx, aLength_0; "__length"
0x18004d00a  lea     rcx, [rsp+208h+var_118]
0x18004d012  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004d017  nop
0x18004d018  lea     rdx, [rsp+208h+var_118]
0x18004d020  lea     rcx, [rsp+208h+var_60]
0x18004d028  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@@std@@@2@@std@@QEAAAEAV?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@1@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,std::variant<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>>::operator[](std::string &&)
0x18004d02d  mov     rbx, rax
0x18004d030  cmp     byte ptr [rax+28h], 1
0x18004d034  jnz     short loc_18004D05F
0x18004d036  mov     [rax], rsi
0x18004d039  mov     [rax+8], r13b
0x18004d03d  mov     ecx, dword ptr [rsp+208h+var_138+9]
0x18004d044  mov     [rax+9], ecx
0x18004d047  movzx   ecx, word ptr [rsp+208h+var_138+0Dh]
0x18004d04f  mov     [rax+0Dh], cx
0x18004d053  mov     al, byte ptr [rsp+208h+var_138+0Fh]
0x18004d05a  mov     [rbx+0Fh], al
0x18004d05d  jmp     short loc_18004D092
0x18004d05f  mov     rcx, rbx
0x18004d062  call    ?_Reset@?$_Variant_base@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@std@@QEAAXXZ; std::_Variant_base<bool,etw_integer,double,etw_pointer,std::string,etw_stack,etw_stack_user,etw_key_stack,std::vector<__int64>,std::vector<std::string>>::_Reset(void)
0x18004d067  mov     [rbx], rsi
0x18004d06a  mov     [rbx+8], r13b
0x18004d06e  mov     eax, dword ptr [rsp+208h+var_138+9]
0x18004d075  mov     [rbx+9], eax
0x18004d078  movzx   eax, word ptr [rsp+208h+var_138+0Dh]
0x18004d080  mov     [rbx+0Dh], ax
0x18004d084  mov     al, byte ptr [rsp+208h+var_138+0Fh]
0x18004d08b  mov     [rbx+0Fh], al
0x18004d08e  mov     byte ptr [rbx+28h], 1
0x18004d092  lea     rcx, [rsp+208h+var_118]
0x18004d09a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004d09f  mov     rbx, [rdi]
0x18004d0a2  lea     rdx, [rsp+208h+var_F8]
0x18004d0aa  lea     rcx, [rsp+208h+var_1E0]
0x18004d0af  call    ??0etw_event@@QEAA@$$QEAU0@@Z; etw_event::etw_event(etw_event &&)
0x18004d0b4  mov     rdx, rax
0x18004d0b7  mov     rcx, rbx; _Mtx_t
0x18004d0ba  call    ?add@?$sync_q@Uetw_event@@@@QEAA_NUetw_event@@_N@Z; sync_q<etw_event>::add(etw_event,bool)
0x18004d0bf  nop
0x18004d0c0  lea     rcx, [rsp+208h+var_60]
0x18004d0c8  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$variant@_NUetw_integer@@NUetw_pointer@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Uetw_stack@@Uetw_stack_user@@Uetw_key_stack@@V?$vector@_JV?$allocator@_J@std@@@4@V?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x18004d0cd  lea     rcx, [rsp+208h+var_80]
0x18004d0d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d0da  lea     rcx, [rsp+208h+var_A0]
0x18004d0e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d0e7  nop
0x18004d0e8  mov     rcx, [rsp+208h+var_48]
0x18004d0f0  xor     rcx, rsp; StackCookie
0x18004d0f3  call    __security_check_cookie
0x18004d0f8  lea     r11, [rsp+208h+var_28]
0x18004d100  mov     rbx, [r11+38h]
0x18004d104  mov     rsi, [r11+40h]
0x18004d108  movaps  xmm6, xmmword ptr [r11-10h]
0x18004d10d  mov     rsp, r11
0x18004d110  pop     r15
0x18004d112  pop     r14
0x18004d114  pop     r13
0x18004d116  pop     r12
0x18004d118  pop     rdi
0x18004d119  retn
```
