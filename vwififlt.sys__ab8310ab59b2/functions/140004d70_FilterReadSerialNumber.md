# FilterReadSerialNumber

- ea: `0x140004d70`
- end: `0x14000507e`
- name: `FilterReadSerialNumber`
- size: `782`
- prototype: `__int64 __fastcall(__int64, int, unsigned __int32 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140004568`

## callees

- `0x14000204c`
- `0x140003634`
- `0x140004d70`
- `0x140005084`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000d9d4`
- `0x14000da74`
- `0x14000dba8`
- `0x14000dd6c`
- `0x14000f110`

## pseudocode

```c
__int64 __fastcall FilterReadSerialNumber(__int64 a1, int a2, unsigned __int32 *a3)
{
  unsigned __int32 v4; // edi
  unsigned int Long; // ebx
  __int64 v8; // rcx
  wchar_t *v9; // rax
  PDEVICE_OBJECT v10; // rcx
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rdx
  int v15; // r8d
  int v16; // edx
  int v17; // r8d
  unsigned __int32 v18[4]; // [rsp+30h] [rbp-858h] BYREF
  wchar_t pszDest[1024]; // [rsp+40h] [rbp-848h] BYREF

  v4 = 0;
  v18[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  Long = RtlStringCbPrintfW(pszDest, 0x800u, L"%s%d", L"SerialNo", a2);
  if ( Long )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v14 = 24;
LABEL_21:
      WPP_SF_d(v10->AttachedDevice, v14, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
    }
  }
  else
  {
    v8 = 1024;
    v9 = pszDest;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v8;
    }
    while ( v8 );
    Long = v8 == 0 ? 0xC000000D : 0;
    if ( v8 )
    {
      Long = filterReadLong(a1, pszDest, v18);
      if ( Long )
      {
        Long = RefreshGlobalSerialNumberFromRegistry();
        if ( !Long )
        {
          v4 = _InterlockedIncrement(&g_ulSerialNo);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_Sdd(WPP_GLOBAL_Control->AttachedDevice, 27, v15, a1 + 160, a2, v4);
          }
          Long = filterWriteLong(0, L"GlobalSerialNoEx", v4);
          if ( Long )
          {
            _InterlockedDecrement(&g_ulSerialNo);
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              v14 = 29;
              goto LABEL_21;
            }
          }
          else
          {
            Long = filterWriteLong(a1, pszDest, v4);
            if ( Long )
            {
              _InterlockedDecrement(&g_ulSerialNo);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_SdD(WPP_GLOBAL_Control->AttachedDevice, v16, v17, a1 + 160, a2, Long);
              }
            }
          }
          goto LABEL_8;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v4 = v18[0];
        WPP_SF_dSd(WPP_GLOBAL_Control->AttachedDevice, v12, v13, v18[0], a1 + 160, a2);
        goto LABEL_8;
      }
      v4 = v18[0];
      goto LABEL_8;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v14 = 25;
      goto LABEL_21;
    }
  }
LABEL_8:
  *a3 = v4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  return Long;
}

```

## disassembly

```asm
0x140004d70  mov     [rsp+arg_18], rbx
0x140004d75  push    rbp
0x140004d76  push    rsi
0x140004d77  push    rdi
0x140004d78  push    r12
0x140004d7a  push    r13
0x140004d7c  push    r14
0x140004d7e  push    r15
0x140004d80  sub     rsp, 850h
0x140004d87  mov     rax, cs:__security_cookie
0x140004d8e  xor     rax, rsp
0x140004d91  mov     [rsp+888h+var_48], rax
0x140004d99  xor     r12d, r12d
0x140004d9c  mov     r14, r8
0x140004d9f  mov     edi, r12d
0x140004da2  mov     [rsp+888h+var_858], r12d
0x140004da7  mov     ebp, edx
0x140004da9  mov     rsi, rcx
0x140004dac  mov     rcx, cs:WPP_GLOBAL_Control
0x140004db3  lea     r15, WPP_GLOBAL_Control
0x140004dba  lea     r13, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x140004dc1  cmp     rcx, r15
0x140004dc4  jnz     loc_140004EAE
0x140004dca  lea     r9, aSerialno; "SerialNo"
0x140004dd1  mov     dword ptr [rsp+888h+var_868], ebp
0x140004dd5  lea     r8, aSD; "%s%d"
0x140004ddc  mov     edx, 800h; cbDest
0x140004de1  lea     rcx, [rsp+888h+pszDest]; pszDest
0x140004de6  call    RtlStringCbPrintfW
0x140004deb  mov     ebx, eax
0x140004ded  test    eax, eax
0x140004def  jnz     loc_140004EF3
0x140004df5  mov     ecx, 400h
0x140004dfa  lea     rax, [rsp+888h+pszDest]
0x140004dff  cmp     [rax], r12w
0x140004e03  jz      short loc_140004E0F
0x140004e05  add     rax, 2
0x140004e09  sub     rcx, 1
0x140004e0d  jnz     short loc_140004DFF
0x140004e0f  mov     rax, rcx
0x140004e12  neg     rax
0x140004e15  sbb     ebx, ebx
0x140004e17  not     ebx
0x140004e19  and     ebx, 0C000000Dh
0x140004e1f  test    rcx, rcx
0x140004e22  jnz     short loc_140004E75
0x140004e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e2b  cmp     rcx, r15
0x140004e2e  jnz     loc_140004F32
0x140004e34  mov     [r14], edi
0x140004e37  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e3e  cmp     rcx, r15
0x140004e41  jnz     loc_140004ECF
0x140004e47  mov     eax, ebx
0x140004e49  mov     rcx, [rsp+888h+var_48]
0x140004e51  xor     rcx, rsp; StackCookie
0x140004e54  call    __security_check_cookie
0x140004e59  mov     rbx, [rsp+888h+arg_18]
0x140004e61  add     rsp, 850h
0x140004e68  pop     r15
0x140004e6a  pop     r14
0x140004e6c  pop     r13
0x140004e6e  pop     r12
0x140004e70  pop     rdi
0x140004e71  pop     rsi
0x140004e72  pop     rbp
0x140004e73  retn
0x140004e75  lea     r8, [rsp+888h+var_858]
0x140004e7a  mov     rcx, rsi
0x140004e7d  lea     rdx, [rsp+888h+pszDest]
0x140004e82  call    filterReadLong
0x140004e87  mov     ebx, eax
0x140004e89  test    eax, eax
0x140004e8b  jnz     loc_140004F3F
0x140004e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e98  cmp     rcx, r15
0x140004e9b  jz      short loc_140004EA8
0x140004e9d  mov     eax, [rcx+2Ch]
0x140004ea0  test    al, 4
0x140004ea2  jnz     loc_140005059
0x140004ea8  mov     edi, [rsp+888h+var_858]
0x140004eac  jmp     short loc_140004E34
0x140004eae  mov     eax, [rcx+2Ch]
0x140004eb1  test    al, 20h
0x140004eb3  jz      loc_140004DCA
0x140004eb9  mov     rcx, [rcx+18h]
0x140004ebd  mov     edx, 17h
0x140004ec2  mov     r8, r13
0x140004ec5  call    WPP_SF_
0x140004eca  jmp     loc_140004DCA
0x140004ecf  mov     eax, [rcx+2Ch]
0x140004ed2  test    al, 20h
0x140004ed4  jz      loc_140004E47
0x140004eda  mov     rcx, [rcx+18h]
0x140004ede  mov     edx, 1Fh
0x140004ee3  mov     r9d, ebx
0x140004ee6  mov     r8, r13
0x140004ee9  call    WPP_SF_d
0x140004eee  jmp     loc_140004E47
0x140004ef3  mov     rcx, cs:WPP_GLOBAL_Control
0x140004efa  cmp     rcx, r15
0x140004efd  jz      loc_140004E34
0x140004f03  mov     edx, [rcx+2Ch]
0x140004f06  test    dl, 1
0x140004f09  jz      loc_140004E34
0x140004f0f  mov     edx, 18h
0x140004f14  mov     r9d, eax
0x140004f17  jmp     short loc_140004F21
0x140004f19  mov     edx, 19h
0x140004f1e  mov     r9d, ebx
0x140004f21  mov     rcx, [rcx+18h]
0x140004f25  mov     r8, r13
0x140004f28  call    WPP_SF_d
0x140004f2d  jmp     loc_140004E34
0x140004f32  mov     eax, [rcx+2Ch]
0x140004f35  test    al, 1
0x140004f37  jz      loc_140004E34
0x140004f3d  jmp     short loc_140004F19
0x140004f3f  call    RefreshGlobalSerialNumberFromRegistry
0x140004f44  mov     ebx, eax
0x140004f46  test    eax, eax
0x140004f48  jz      short loc_140004F7E
0x140004f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f51  cmp     rcx, r15
0x140004f54  jz      loc_140004EA8
0x140004f5a  mov     eax, [rcx+2Ch]
0x140004f5d  test    al, 1
0x140004f5f  jz      loc_140004EA8
0x140004f65  mov     rcx, [rcx+18h]
0x140004f69  mov     edx, 1Ah
0x140004f6e  mov     r9d, ebx
0x140004f71  mov     r8, r13
0x140004f74  call    WPP_SF_d
0x140004f79  jmp     loc_140004EA8
0x140004f7e  mov     edi, 1
0x140004f83  lock xadd cs:g_ulSerialNo, edi
0x140004f8b  inc     edi
0x140004f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f94  cmp     rcx, r15
0x140004f97  jz      short loc_140004FBD
0x140004f99  mov     eax, [rcx+2Ch]
0x140004f9c  test    al, 4
0x140004f9e  jz      short loc_140004FBD
0x140004fa0  mov     rcx, [rcx+18h]
0x140004fa4  lea     r9, [rsi+0A0h]
0x140004fab  mov     edx, 1Bh
0x140004fb0  mov     [rsp+888h+var_860], edi
0x140004fb4  mov     dword ptr [rsp+888h+var_868], ebp
0x140004fb8  call    WPP_SF_Sdd
0x140004fbd  mov     r8d, edi
0x140004fc0  lea     rdx, aGlobalserialno_0; "GlobalSerialNoEx"
0x140004fc7  xor     ecx, ecx
0x140004fc9  call    filterWriteLong
0x140004fce  mov     ebx, eax
0x140004fd0  test    eax, eax
0x140004fd2  jnz     short loc_14000502D
0x140004fd4  mov     r8d, edi
0x140004fd7  lea     rdx, [rsp+888h+pszDest]
0x140004fdc  mov     rcx, rsi
0x140004fdf  call    filterWriteLong
0x140004fe4  mov     ebx, eax
0x140004fe6  test    eax, eax
0x140004fe8  jz      loc_140004E34
0x140004fee  lock dec cs:g_ulSerialNo
0x140004ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ffc  cmp     rcx, r15
0x140004fff  jz      loc_140004E34
0x140005005  mov     eax, [rcx+2Ch]
0x140005008  test    al, 1
0x14000500a  jz      loc_140004E34
0x140005010  mov     rcx, [rcx+18h]
0x140005014  lea     r9, [rsi+0A0h]
0x14000501b  mov     [rsp+888h+var_860], ebx
0x14000501f  mov     dword ptr [rsp+888h+var_868], ebp
0x140005023  call    WPP_SF_SdD
0x140005028  jmp     loc_140004E34
0x14000502d  lock dec cs:g_ulSerialNo
0x140005034  mov     rcx, cs:WPP_GLOBAL_Control
0x14000503b  cmp     rcx, r15
0x14000503e  jz      loc_140004E34
0x140005044  mov     eax, [rcx+2Ch]
0x140005047  test    al, 1
0x140005049  jz      loc_140004E34
0x14000504f  mov     edx, 1Dh
0x140005054  jmp     loc_140004F1E
0x140005059  mov     edi, [rsp+888h+var_858]
0x14000505d  lea     rax, [rsi+0A0h]
0x140005064  mov     rcx, [rcx+18h]
0x140005068  mov     r9d, edi
0x14000506b  mov     [rsp+888h+var_860], ebp
0x14000506f  mov     [rsp+888h+var_868], rax
0x140005074  call    WPP_SF_dSd
0x140005079  jmp     loc_140004E34
```
