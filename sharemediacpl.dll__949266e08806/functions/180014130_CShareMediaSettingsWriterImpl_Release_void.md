# CShareMediaSettingsWriterImpl::Release(void)

- ea: `0x180014130`
- end: `0x1800141d1`
- name: `?Release@CShareMediaSettingsWriterImpl@@UEAAKXZ`
- size: `161`
- prototype: `unsigned int __fastcall(CShareMediaSettingsWriterImpl *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x180001954`
- `0x180003860`
- `0x180003888`
- `0x180013cbc`
- `0x180014130`

## pseudocode

```c
__int64 __fastcall CShareMediaSettingsWriterImpl::Release(CShareMediaSettingsWriterImpl *this)
{
  unsigned __int32 v2; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids);
  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    CShareMediaSettingsWriterImpl::~CShareMediaSettingsWriterImpl(this);
    operator delete(this);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180014130  mov     [rsp+arg_0], rbx
0x180014135  mov     [rsp+arg_8], rsi
0x18001413a  push    rdi
0x18001413b  sub     rsp, 20h
0x18001413f  mov     rdi, rcx
0x180014142  mov     rcx, cs:WPP_GLOBAL_Control
0x180014149  lea     rsi, WPP_GLOBAL_Control
0x180014150  cmp     rcx, rsi
0x180014153  jz      short loc_180014170
0x180014155  test    byte ptr [rcx+1Ch], 20h
0x180014159  jz      short loc_180014170
0x18001415b  mov     rcx, [rcx+10h]
0x18001415f  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x180014166  mov     edx, 12h
0x18001416b  call    WPP_SF_
0x180014170  or      ebx, 0FFFFFFFFh
0x180014173  lock xadd [rdi+8], ebx
0x180014178  sub     ebx, 1
0x18001417b  jnz     short loc_180014195
0x18001417d  test    rdi, rdi
0x180014180  jz      short loc_180014195
0x180014182  mov     rcx, rdi; this
0x180014185  call    ??1CShareMediaSettingsWriterImpl@@QEAA@XZ; CShareMediaSettingsWriterImpl::~CShareMediaSettingsWriterImpl(void)
0x18001418a  lea     edx, [rbx+10h]
0x18001418d  mov     rcx, rdi; Block
0x180014190  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014195  mov     rcx, cs:WPP_GLOBAL_Control
0x18001419c  cmp     rcx, rsi
0x18001419f  jz      short loc_1800141BF
0x1800141a1  test    byte ptr [rcx+1Ch], 20h
0x1800141a5  jz      short loc_1800141BF
0x1800141a7  mov     rcx, [rcx+10h]
0x1800141ab  lea     r8, WPP_2387886db1143477e2ca94a8625aeb31_Traceguids
0x1800141b2  mov     edx, 13h
0x1800141b7  mov     r9d, ebx
0x1800141ba  call    WPP_SF_d
0x1800141bf  mov     rsi, [rsp+28h+arg_8]
0x1800141c4  mov     eax, ebx
0x1800141c6  mov     rbx, [rsp+28h+arg_0]
0x1800141cb  add     rsp, 20h
0x1800141cf  pop     rdi
0x1800141d0  retn
```
