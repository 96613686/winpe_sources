# StopComTask

- ea: `0x140001d30`
- end: `0x140001e17`
- name: `StopComTask`
- size: `231`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140001d30`
- `0x1400093b0`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall StopComTask(_QWORD *a1)
{
  _QWORD *v1; // rbx
  unsigned int v2; // ebx
  signed int v4; // eax
  wmi::Exception *v5; // [rsp+30h] [rbp-18h] BYREF
  _com_error *v6; // [rsp+38h] [rbp-10h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h]

  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v1 = a1;
    v8 = *a1;
    v4 = (*(__int64 (__fastcall **)(ComTaskMgrWnd *, _QWORD *))(*(_QWORD *)ComTaskMgrBase::s_pVirtualSingleton + 8LL))(
           ComTaskMgrBase::s_pVirtualSingleton,
           a1);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v5) )
    {
      v4 = (**(__int64 (__fastcall ***)(wmi::Exception *))v5)(v5);
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      v1 = a1;
      __eh34_try_continuation(0, &wmi::Exception `RTTI Type Descriptor', &loc_140001D5E);
      goto LABEL_2;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      *a1 = 0;
      v2 = 14;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140001D60);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &std::invalid_argument `RTTI Type Descriptor', 0) )
    {
      *a1 = 0;
      v2 = 87;
      __eh34_try_continuation(0, &std::invalid_argument `RTTI Type Descriptor', &loc_140001D71);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &std::length_error `RTTI Type Descriptor', 0) )
    {
      *a1 = 0;
      v2 = 87;
      __eh34_try_continuation(0, &std::length_error `RTTI Type Descriptor', &loc_140001D82);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &std::out_of_range `RTTI Type Descriptor', 0) )
    {
      *a1 = 0;
      v2 = 87;
      __eh34_try_continuation(0, &std::out_of_range `RTTI Type Descriptor', &loc_140001D93);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
    {
      *a1 = 0;
      v2 = 16389;
      __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_140001DA4);
      goto LABEL_5;
    }
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v6) )
    {
      v4 = *((_DWORD *)v6 + 2);
      v1 = a1;
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_140001DB5);
    }
  }
LABEL_2:
  *v1 = 0;
  if ( v4 >= 0 )
    return 0;
  v2 = (unsigned __int16)v4;
  if ( !(_WORD)v4 )
    v2 = 6;
LABEL_5:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids, v8, v2);
  return v2;
}

```

## disassembly

```asm
0x140001d30  mov     [rsp+arg_0], rcx
0x140001d35  push    rbx
0x140001d36  sub     rsp, 40h
0x140001d3a  mov     rbx, rcx
0x140001d3d  mov     rax, [rcx]
0x140001d40  mov     [rsp+48h+arg_10], rax
0x140001d45  mov     rcx, cs:?s_pVirtualSingleton@ComTaskMgrBase@@0PEAV1@EA; ComTaskMgrBase * ComTaskMgrBase::s_pVirtualSingleton
0x140001d4c  mov     rax, [rcx]
0x140001d4f  mov     rdx, rbx
0x140001d52  mov     rax, [rax+8]
0x140001d56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d5b  nop
0x140001d5c  jmp     short loc_140001DBE
0x140001d5e  jmp     short loc_140001DB5
0x140001d60  xor     ecx, ecx
0x140001d62  mov     rax, [rsp+48h+arg_0]
0x140001d67  mov     [rax], rcx
0x140001d6a  mov     ebx, 0Eh
0x140001d6f  jmp     short loc_140001DD4
0x140001d71  xor     ecx, ecx
0x140001d73  mov     rax, [rsp+48h+arg_0]
0x140001d78  mov     [rax], rcx
0x140001d7b  mov     ebx, 57h ; 'W'
0x140001d80  jmp     short loc_140001DD4
0x140001d82  xor     ecx, ecx
0x140001d84  mov     rax, [rsp+48h+arg_0]
0x140001d89  mov     [rax], rcx
0x140001d8c  mov     ebx, 57h ; 'W'
0x140001d91  jmp     short loc_140001DD4
0x140001d93  xor     ecx, ecx
0x140001d95  mov     rax, [rsp+48h+arg_0]
0x140001d9a  mov     [rax], rcx
0x140001d9d  mov     ebx, 57h ; 'W'
0x140001da2  jmp     short loc_140001DD4
0x140001da4  xor     ecx, ecx
0x140001da6  mov     rax, [rsp+48h+arg_0]
0x140001dab  mov     [rax], rcx
0x140001dae  mov     ebx, 4005h
0x140001db3  jmp     short loc_140001DD4
0x140001db5  mov     eax, [rsp+48h+arg_8]
0x140001db9  mov     rbx, [rsp+48h+arg_0]
0x140001dbe  xor     ecx, ecx
0x140001dc0  mov     [rbx], rcx
0x140001dc3  test    eax, eax
0x140001dc5  jns     short loc_140001E0F
0x140001dc7  movzx   ebx, ax
0x140001dca  mov     eax, 6
0x140001dcf  test    ebx, ebx
0x140001dd1  cmovz   ebx, eax
0x140001dd4  lea     rax, WPP_GLOBAL_Control
0x140001ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001de2  cmp     rcx, rax
0x140001de5  jz      short loc_140001E0B
0x140001de7  test    byte ptr [rcx+1Ch], 1
0x140001deb  jz      short loc_140001E0B
0x140001ded  mov     edx, 0Fh
0x140001df2  mov     [rsp+48h+var_28], ebx
0x140001df6  mov     r9, [rsp+48h+arg_10]
0x140001dfb  lea     r8, WPP_fd76d537424c3f213087d14e42e29f74_Traceguids
0x140001e02  mov     rcx, [rcx+10h]
0x140001e06  call    WPP_SF_qd
0x140001e0b  mov     eax, ebx
0x140001e0d  jmp     short loc_140001E11
0x140001e0f  mov     eax, ecx
0x140001e11  add     rsp, 40h
0x140001e15  pop     rbx
0x140001e16  retn
```
