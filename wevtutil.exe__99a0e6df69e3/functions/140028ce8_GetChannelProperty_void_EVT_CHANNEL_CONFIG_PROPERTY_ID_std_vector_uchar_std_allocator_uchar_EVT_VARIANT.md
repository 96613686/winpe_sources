# GetChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar,std::allocator<uchar>> &,_EVT_VARIANT * &)

- ea: `0x140028ce8`
- end: `0x140028e4c`
- name: `?GetChannelProperty@@YAKPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z`
- size: `356`
- prototype: `__int64 __fastcall(EVT_HANDLE ChannelConfig, EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140011f60`
- `0x1400260f8`
- `0x1400262e4`

## callees

- `0x140022510`
- `0x140028a80`
- `0x140028ce8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e27`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x140028d7e`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x140028e1d`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x140028d7e`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x140028e1d`

## pseudocode

```c
__int64 __fastcall GetChannelProperty(
        EVT_HANDLE ChannelConfig,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId,
        __int64 a3,
        struct _EVT_VARIANT **a4)
{
  char *v4; // rsi
  struct _EVT_VARIANT *v6; // r10
  unsigned __int64 v8; // r8
  struct _EVT_VARIANT *v11; // rax
  unsigned __int64 v12; // rdi
  struct _EVT_VARIANT *PropertyValueBuffer; // rax
  DWORD LastError; // edi
  __int64 v15; // rsi
  struct _EVT_VARIANT *v16; // rdx
  unsigned __int64 v17; // rcx
  size_t v18; // rax
  size_t v19; // rdi
  struct _EVT_VARIANT *v20; // rax
  struct _EVT_VARIANT *v21; // rax
  DWORD PropertyValueBufferUsed; // [rsp+80h] [rbp+18h] BYREF

  v4 = *(char **)(a3 + 8);
  v6 = *(struct _EVT_VARIANT **)a3;
  v8 = (unsigned __int64)&v4[-*(_QWORD *)a3];
  if ( v8 <= 0x10 )
  {
    if ( v8 >= 0x10 )
      goto LABEL_8;
    if ( *(_QWORD *)(a3 + 16) - (_QWORD)v6 < 0x10u )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, 16);
      goto LABEL_8;
    }
    v12 = 16 - v8;
    memset_0(v4, 0, 16 - v8);
    v11 = (struct _EVT_VARIANT *)&v4[v12];
  }
  else
  {
    v11 = v6 + 1;
  }
  *(_QWORD *)(a3 + 8) = v11;
LABEL_8:
  PropertyValueBuffer = *(struct _EVT_VARIANT **)a3;
  PropertyValueBufferUsed = *(_DWORD *)(a3 + 8) - *(_QWORD *)a3;
  LastError = 0;
  if ( EvtGetChannelConfigProperty(
         ChannelConfig,
         PropertyId,
         0,
         PropertyValueBufferUsed,
         PropertyValueBuffer,
         &PropertyValueBufferUsed) )
  {
LABEL_21:
    v21 = *(struct _EVT_VARIANT **)a3;
    goto LABEL_22;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
    goto LABEL_19;
  v15 = *(_QWORD *)(a3 + 8);
  v16 = *(struct _EVT_VARIANT **)a3;
  v17 = v15 - *(_QWORD *)a3;
  if ( PropertyValueBufferUsed >= v17 )
  {
    if ( PropertyValueBufferUsed <= v17 )
      goto LABEL_17;
    if ( (unsigned __int64)PropertyValueBufferUsed > *(_QWORD *)(a3 + 16) - (_QWORD)v16 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, PropertyValueBufferUsed);
      goto LABEL_17;
    }
    v19 = PropertyValueBufferUsed - v17;
    memset_0(*(void **)(a3 + 8), 0, v19);
    v18 = v19 + v15;
  }
  else
  {
    v18 = (size_t)v16 + PropertyValueBufferUsed;
  }
  *(_QWORD *)(a3 + 8) = v18;
LABEL_17:
  v20 = *(struct _EVT_VARIANT **)a3;
  PropertyValueBufferUsed = *(_DWORD *)(a3 + 8) - *(_QWORD *)a3;
  LastError = 0;
  if ( EvtGetChannelConfigProperty(ChannelConfig, PropertyId, 0, PropertyValueBufferUsed, v20, &PropertyValueBufferUsed) )
    goto LABEL_21;
  LastError = GetLastError();
LABEL_19:
  if ( !LastError )
    goto LABEL_21;
  v21 = 0;
LABEL_22:
  *a4 = v21;
  return LastError;
}

```

## disassembly

```asm
0x140028ce8  push    rbx
0x140028cea  push    rbp
0x140028ceb  push    rsi
0x140028cec  push    rdi
0x140028ced  push    r14
0x140028cef  push    r15
0x140028cf1  sub     rsp, 38h
0x140028cf5  mov     rsi, [r8+8]
0x140028cf9  mov     rbx, r8
0x140028cfc  mov     r10, [r8]
0x140028cff  mov     edi, 10h
0x140028d04  mov     r8, rsi
0x140028d07  mov     r14, r9
0x140028d0a  sub     r8, r10
0x140028d0d  mov     ebp, edx
0x140028d0f  mov     r15, rcx
0x140028d12  cmp     r8, rdi
0x140028d15  jbe     short loc_140028D1D
0x140028d17  lea     rax, [r10+10h]
0x140028d1b  jmp     short loc_140028D4C
0x140028d1d  jnb     short loc_140028D50
0x140028d1f  mov     rax, [rbx+10h]
0x140028d23  sub     rax, r10
0x140028d26  cmp     rax, rdi
0x140028d29  jnb     short loc_140028D38
0x140028d2b  mov     rdx, rdi
0x140028d2e  mov     rcx, rbx
0x140028d31  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140028d36  jmp     short loc_140028D50
0x140028d38  sub     rdi, r8
0x140028d3b  xor     edx, edx; Val
0x140028d3d  mov     r8, rdi; Size
0x140028d40  mov     rcx, rsi; void *
0x140028d43  call    memset_0
0x140028d48  lea     rax, [rdi+rsi]
0x140028d4c  mov     [rbx+8], rax
0x140028d50  mov     rax, [rbx]
0x140028d53  lea     rcx, [rsp+68h+arg_10]
0x140028d5b  mov     r9d, [rbx+8]
0x140028d5f  xor     r8d, r8d; Flags
0x140028d62  mov     [rsp+68h+PropertyValueBufferUsed], rcx; PropertyValueBufferUsed
0x140028d67  sub     r9d, eax; PropertyValueBufferSize
0x140028d6a  mov     rcx, r15; ChannelConfig
0x140028d6d  mov     [rsp+68h+arg_10], r9d
0x140028d75  mov     edx, ebp; PropertyId
0x140028d77  mov     [rsp+68h+PropertyValueBuffer], rax; PropertyValueBuffer
0x140028d7c  xor     edi, edi
0x140028d7e  call    cs:__imp_EvtGetChannelConfigProperty
0x140028d84  test    eax, eax
0x140028d86  jnz     loc_140028E37
0x140028d8c  call    cs:__imp_GetLastError
0x140028d92  mov     edi, eax
0x140028d94  cmp     eax, 7Ah ; 'z'
0x140028d97  jnz     loc_140028E2F
0x140028d9d  mov     rsi, [rbx+8]
0x140028da1  mov     rdx, [rbx]
0x140028da4  mov     rcx, rsi
0x140028da7  mov     edi, [rsp+68h+arg_10]
0x140028dae  sub     rcx, rdx
0x140028db1  cmp     rdi, rcx
0x140028db4  jnb     short loc_140028DBC
0x140028db6  lea     rax, [rdi+rdx]
0x140028dba  jmp     short loc_140028DEB
0x140028dbc  jbe     short loc_140028DEF
0x140028dbe  mov     rax, [rbx+10h]
0x140028dc2  sub     rax, rdx
0x140028dc5  cmp     rdi, rax
0x140028dc8  jbe     short loc_140028DD7
0x140028dca  mov     rdx, rdi
0x140028dcd  mov     rcx, rbx
0x140028dd0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140028dd5  jmp     short loc_140028DEF
0x140028dd7  sub     rdi, rcx
0x140028dda  xor     edx, edx; Val
0x140028ddc  mov     r8, rdi; Size
0x140028ddf  mov     rcx, rsi; void *
0x140028de2  call    memset_0
0x140028de7  lea     rax, [rdi+rsi]
0x140028deb  mov     [rbx+8], rax
0x140028def  mov     rax, [rbx]
0x140028df2  lea     rcx, [rsp+68h+arg_10]
0x140028dfa  mov     r9d, [rbx+8]
0x140028dfe  xor     r8d, r8d; Flags
0x140028e01  mov     [rsp+68h+PropertyValueBufferUsed], rcx; PropertyValueBufferUsed
0x140028e06  sub     r9d, eax; PropertyValueBufferSize
0x140028e09  mov     rcx, r15; ChannelConfig
0x140028e0c  mov     [rsp+68h+arg_10], r9d
0x140028e14  mov     edx, ebp; PropertyId
0x140028e16  mov     [rsp+68h+PropertyValueBuffer], rax; PropertyValueBuffer
0x140028e1b  xor     edi, edi
0x140028e1d  call    cs:__imp_EvtGetChannelConfigProperty
0x140028e23  test    eax, eax
0x140028e25  jnz     short loc_140028E37
0x140028e27  call    cs:__imp_GetLastError
0x140028e2d  mov     edi, eax
0x140028e2f  test    edi, edi
0x140028e31  jz      short loc_140028E37
0x140028e33  xor     eax, eax
0x140028e35  jmp     short loc_140028E3A
0x140028e37  mov     rax, [rbx]
0x140028e3a  mov     [r14], rax
0x140028e3d  mov     eax, edi
0x140028e3f  add     rsp, 38h
0x140028e43  pop     r15
0x140028e45  pop     r14
0x140028e47  pop     rdi
0x140028e48  pop     rsi
0x140028e49  pop     rbp
0x140028e4a  pop     rbx
0x140028e4b  retn
```
