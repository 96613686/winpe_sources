# InitializeComTasksLib

- ea: `0x140001860`
- end: `0x140001960`
- name: `InitializeComTasksLib`
- size: `256`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140001860`
- `0x140001968`
- `0x140009330`
- `0x140009400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140001953`
- `api-ms-win-core-processthreads-l1-1-0!SetProcessShutdownParameters` at `0x140001953`

## pseudocode

```c
__int64 __fastcall InitializeComTasksLib(HINSTANCE a1)
{
  unsigned int v2; // ebx
  signed int v4; // eax
  wmi::Exception *v5; // [rsp+20h] [rbp-18h] BYREF
  _com_error *v6; // [rsp+28h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v4 = ComTaskMgrBase::Initialize(a1);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v5) )
    {
      v4 = (**(__int64 (__fastcall ***)(wmi::Exception *))v5)(v5);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      __eh34_try_continuation(0, &wmi::Exception `RTTI Type Descriptor', &loc_1400018EB);
      goto LABEL_4;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v2 = 14;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1400018ED);
      goto LABEL_7;
    }
    if ( __eh34_catch_type(0, &std::invalid_argument `RTTI Type Descriptor', 0) )
    {
      v2 = 87;
      __eh34_try_continuation(0, &std::invalid_argument `RTTI Type Descriptor', &loc_1400018FB);
      goto LABEL_7;
    }
    if ( __eh34_catch_type(0, &std::length_error `RTTI Type Descriptor', 0) )
    {
      v2 = 87;
      __eh34_try_continuation(0, &std::length_error `RTTI Type Descriptor', &loc_140001909);
      goto LABEL_7;
    }
    if ( __eh34_catch_type(0, &std::out_of_range `RTTI Type Descriptor', 0) )
    {
      v2 = 87;
      __eh34_try_continuation(0, &std::out_of_range `RTTI Type Descriptor', &loc_140001917);
      goto LABEL_7;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      v2 = 16389;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140001928);
      goto LABEL_7;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v6) )
    {
      v4 = *((_DWORD *)v6 + 2);
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_140001939);
    }
  }
LABEL_4:
  if ( v4 >= 0 )
  {
    SetProcessShutdownParameters(0x7Fu, 1u);
    return 0;
  }
  v2 = (unsigned __int16)v4;
  if ( !(_WORD)v4 )
    v2 = 6;
LABEL_7:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x140001860  mov     [rsp+arg_0], rbx
0x140001865  push    rdi
0x140001866  sub     rsp, 30h
0x14000186a  mov     rbx, rcx
0x14000186d  lea     rdi, WPP_GLOBAL_Control
0x140001874  mov     rcx, cs:WPP_GLOBAL_Control
0x14000187b  cmp     rcx, rdi
0x14000187e  jz      short loc_140001886
0x140001880  test    byte ptr [rcx+1Ch], 4
0x140001884  jnz     short loc_1400018DB
0x140001886  mov     rcx, rbx; HINSTANCE
0x140001889  call    ?Initialize@ComTaskMgrBase@@SAJPEAUHINSTANCE__@@@Z; ComTaskMgrBase::Initialize(HINSTANCE__ *)
0x14000188e  nop
0x14000188f  test    eax, eax
0x140001891  jns     loc_140001949
0x140001897  movzx   ebx, ax
0x14000189a  mov     eax, 6
0x14000189f  test    ebx, ebx
0x1400018a1  cmovz   ebx, eax
0x1400018a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018ab  cmp     rcx, rdi
0x1400018ae  jz      short loc_1400018CE
0x1400018b0  test    byte ptr [rcx+1Ch], 1
0x1400018b4  jz      short loc_1400018CE
0x1400018b6  mov     edx, 0Bh
0x1400018bb  mov     r9d, ebx
0x1400018be  lea     r8, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids
0x1400018c5  mov     rcx, [rcx+10h]
0x1400018c9  call    WPP_SF_d
0x1400018ce  mov     eax, ebx
0x1400018d0  mov     rbx, [rsp+38h+arg_0]
0x1400018d5  add     rsp, 30h
0x1400018d9  pop     rdi
0x1400018da  retn
0x1400018db  mov     edx, 0Ah
0x1400018e0  mov     rcx, [rcx+10h]
0x1400018e4  call    WPP_SF_
0x1400018e9  jmp     short loc_140001886
0x1400018eb  jmp     short loc_140001939
0x1400018ed  mov     ebx, 0Eh
0x1400018f2  lea     rdi, WPP_GLOBAL_Control
0x1400018f9  jmp     short loc_1400018A4
0x1400018fb  mov     ebx, 57h ; 'W'
0x140001900  lea     rdi, WPP_GLOBAL_Control
0x140001907  jmp     short loc_1400018A4
0x140001909  mov     ebx, 57h ; 'W'
0x14000190e  lea     rdi, WPP_GLOBAL_Control
0x140001915  jmp     short loc_1400018A4
0x140001917  mov     ebx, 57h ; 'W'
0x14000191c  lea     rdi, WPP_GLOBAL_Control
0x140001923  jmp     loc_1400018A4
0x140001928  mov     ebx, 4005h
0x14000192d  lea     rdi, WPP_GLOBAL_Control
0x140001934  jmp     loc_1400018A4
0x140001939  mov     eax, [rsp+38h+arg_8]
0x14000193d  lea     rdi, WPP_GLOBAL_Control
0x140001944  jmp     loc_14000188F
0x140001949  mov     edx, 1; dwFlags
0x14000194e  mov     ecx, 7Fh; dwLevel
0x140001953  call    cs:__imp_SetProcessShutdownParameters
0x140001959  xor     eax, eax
0x14000195b  jmp     loc_1400018D0
```
