# CShareMediaSettingsWriterImpl::AddRef(void)

- ea: `0x180013d40`
- end: `0x180013dc8`
- name: `?AddRef@CShareMediaSettingsWriterImpl@@UEAAKXZ`
- size: `136`
- prototype: `unsigned int __fastcall(CShareMediaSettingsWriterImpl *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003860`
- `0x180003888`
- `0x180013d40`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::AddRef(CShareMediaSettingsWriterImpl *this)
{
  signed __int32 v2; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  v2 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 1u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_2387886db1143477e2ca94a8625aeb31_Traceguids,
      (unsigned int)(v2 + 1));
  return (unsigned int)(v2 + 1);
}

```

## disassembly

```asm
0x180013d40  mov     [rsp+arg_0], rbx
0x180013d45  mov     [rsp+arg_8], rsi
0x180013d4a  push    rdi
0x180013d4b  sub     rsp, 20h
0x180013d4f  mov     rdi, rcx
0x180013d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d59  lea     rsi, WPP_GLOBAL_Control
0x180013d60  cmp     rcx, rsi
0x180013d63  jz      short loc_180013D80
0x180013d65  test    byte ptr [rcx+1Ch], 20h
0x180013d69  jz      short loc_180013D80
0x180013d6b  mov     rcx, [rcx+10h]
0x180013d6f  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013d76  mov     edx, 10h
0x180013d7b  call    WPP_SF_
0x180013d80  mov     ebx, 1
0x180013d85  lock xadd [rdi+8], ebx
0x180013d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d91  cmp     rcx, rsi
0x180013d94  jz      short loc_180013DB5
0x180013d96  test    byte ptr [rcx+1Ch], 20h
0x180013d9a  jz      short loc_180013DB5
0x180013d9c  mov     rcx, [rcx+10h]
0x180013da0  lea     r9d, [rbx+1]
0x180013da4  mov     edx, 11h
0x180013da9  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180013db0  call    WPP_SF_d
0x180013db5  mov     rsi, [rsp+28h+arg_8]
0x180013dba  lea     eax, [rbx+1]
0x180013dbd  mov     rbx, [rsp+28h+arg_0]
0x180013dc2  add     rsp, 20h
0x180013dc6  pop     rdi
0x180013dc7  retn
```
