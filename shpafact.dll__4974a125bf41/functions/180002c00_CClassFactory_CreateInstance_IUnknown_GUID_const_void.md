# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002c00`
- end: `0x180002d61`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `353`
- prototype: `int(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001d90`
- `0x180001e4c`
- `0x1800026ac`
- `0x1800026d4`
- `0x180002c00`
- `0x180002dec`
- `0x180002f3c`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v4; // rdi
  unsigned int Instance; // eax
  unsigned int IsValidVirtualFactory; // eax
  unsigned int v9; // ebx

  *a4 = 0;
  v4 = (const struct _GUID *)((char *)this + 8);
  if ( *(_OWORD *)((char *)this + 8) == *(_OWORD *)&CLSID_MultiObjectElevationFactory )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids);
    Instance = CElevatedFactoryClient::CreateInstance(a3, a4);
LABEL_17:
    v9 = Instance;
LABEL_18:
    if ( (v9 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids, v9);
    }
    return v9;
  }
  if ( *(_QWORD *)&v4->Data1 == *(_QWORD *)&CLSID_ElevatedFactoryServerManager.Data1
    && *((_QWORD *)this + 2) == *(_QWORD *)CLSID_ElevatedFactoryServerManager.Data4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids);
    Instance = CElevatedFactoryServerManager::GetSingleton(a3, a4);
    goto LABEL_17;
  }
  IsValidVirtualFactory = _IsValidVirtualFactory(v4);
  v9 = IsValidVirtualFactory;
  if ( !IsValidVirtualFactory )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids);
    Instance = CElevatedFactoryServer::CreateInstance(v4, a3, a4);
    goto LABEL_17;
  }
  if ( IsValidVirtualFactory != 1 )
    goto LABEL_18;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x180002c00  push    rbx
0x180002c02  push    rbp
0x180002c03  push    rsi
0x180002c04  push    rdi
0x180002c05  push    r14
0x180002c07  push    r15
0x180002c09  sub     rsp, 28h
0x180002c0d  mov     qword ptr [r9], 0
0x180002c14  lea     rdi, [rcx+8]
0x180002c18  mov     rax, [rdi]
0x180002c1b  lea     r14, WPP_GLOBAL_Control
0x180002c22  cmp     rax, qword ptr cs:CLSID_MultiObjectElevationFactory.Data1
0x180002c29  lea     r15, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids
0x180002c30  mov     rsi, r9
0x180002c33  mov     rbp, r8
0x180002c36  jnz     short loc_180002C78
0x180002c38  mov     rax, [rdi+8]
0x180002c3c  cmp     rax, qword ptr cs:CLSID_MultiObjectElevationFactory.Data4
0x180002c43  jnz     short loc_180002C78
0x180002c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c4c  cmp     rcx, r14
0x180002c4f  jz      short loc_180002C68
0x180002c51  test    byte ptr [rcx+1Ch], 8
0x180002c55  jz      short loc_180002C68
0x180002c57  mov     rcx, [rcx+10h]
0x180002c5b  mov     edx, 0Ch
0x180002c60  mov     r8, r15
0x180002c63  call    WPP_SF_
0x180002c68  mov     rdx, rsi; void **
0x180002c6b  mov     rcx, rbp; struct _GUID *
0x180002c6e  call    ?CreateInstance@CElevatedFactoryClient@@SAJAEBU_GUID@@PEAPEAX@Z; CElevatedFactoryClient::CreateInstance(_GUID const &,void * *)
0x180002c73  jmp     loc_180002CFE
0x180002c78  mov     rax, [rdi]
0x180002c7b  cmp     rax, qword ptr cs:CLSID_ElevatedFactoryServerManager.Data1
0x180002c82  jnz     short loc_180002CC1
0x180002c84  mov     rax, [rdi+8]
0x180002c88  cmp     rax, qword ptr cs:CLSID_ElevatedFactoryServerManager.Data4
0x180002c8f  jnz     short loc_180002CC1
0x180002c91  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c98  cmp     rcx, r14
0x180002c9b  jz      short loc_180002CB4
0x180002c9d  test    byte ptr [rcx+1Ch], 8
0x180002ca1  jz      short loc_180002CB4
0x180002ca3  mov     rcx, [rcx+10h]
0x180002ca7  mov     edx, 0Dh
0x180002cac  mov     r8, r15
0x180002caf  call    WPP_SF_
0x180002cb4  mov     rdx, rsi; void **
0x180002cb7  mov     rcx, rbp; struct _GUID *
0x180002cba  call    ?GetSingleton@CElevatedFactoryServerManager@@SAJAEBU_GUID@@PEAPEAX@Z; CElevatedFactoryServerManager::GetSingleton(_GUID const &,void * *)
0x180002cbf  jmp     short loc_180002CFE
0x180002cc1  mov     rcx, rdi; struct _GUID *
0x180002cc4  call    ?_IsValidVirtualFactory@@YAJAEBU_GUID@@@Z; _IsValidVirtualFactory(_GUID const &)
0x180002cc9  mov     ebx, eax
0x180002ccb  test    eax, eax
0x180002ccd  jnz     short loc_180002D39
0x180002ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd6  cmp     rcx, r14
0x180002cd9  jz      short loc_180002CF0
0x180002cdb  test    byte ptr [rcx+1Ch], 8
0x180002cdf  jz      short loc_180002CF0
0x180002ce1  mov     rcx, [rcx+10h]
0x180002ce5  lea     edx, [rax+0Eh]
0x180002ce8  mov     r8, r15
0x180002ceb  call    WPP_SF_
0x180002cf0  mov     r8, rsi; void **
0x180002cf3  mov     rdx, rbp; struct _GUID *
0x180002cf6  mov     rcx, rdi; struct _GUID *
0x180002cf9  call    ?CreateInstance@CElevatedFactoryServer@@SAJAEBU_GUID@@0PEAPEAX@Z; CElevatedFactoryServer::CreateInstance(_GUID const &,_GUID const &,void * *)
0x180002cfe  mov     ebx, eax
0x180002d00  test    ebx, ebx
0x180002d02  jns     short loc_180002D2A
0x180002d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d0b  cmp     rcx, r14
0x180002d0e  jz      short loc_180002D2A
0x180002d10  test    byte ptr [rcx+1Ch], 4
0x180002d14  jz      short loc_180002D2A
0x180002d16  mov     rcx, [rcx+10h]
0x180002d1a  mov     edx, 10h
0x180002d1f  mov     r9d, ebx
0x180002d22  mov     r8, r15
0x180002d25  call    WPP_SF_d
0x180002d2a  mov     eax, ebx
0x180002d2c  add     rsp, 28h
0x180002d30  pop     r15
0x180002d32  pop     r14
0x180002d34  pop     rdi
0x180002d35  pop     rsi
0x180002d36  pop     rbp
0x180002d37  pop     rbx
0x180002d38  retn
0x180002d39  cmp     eax, 1
0x180002d3c  jnz     short loc_180002D00
0x180002d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d45  cmp     rcx, r14
0x180002d48  jz      short loc_180002D2A
0x180002d4a  test    byte ptr [rcx+1Ch], 4
0x180002d4e  jz      short loc_180002D2A
0x180002d50  mov     rcx, [rcx+10h]
0x180002d54  lea     edx, [rax+0Eh]
0x180002d57  mov     r8, r15
0x180002d5a  call    WPP_SF_
0x180002d5f  jmp     short loc_180002D2A
```
