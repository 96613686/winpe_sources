# SensInitialize(void)

- ea: `0x180007ecc`
- end: `0x1800080d6`
- name: `?SensInitialize@@YAHXZ`
- size: `522`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007164`

## callees

- `0x180007748`
- `0x1800079a8`
- `0x180007dd0`
- `0x180007ecc`
- `0x1800080dc`
- `0x1800093b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800080be`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800080be`

## pseudocode

```c
__int64 SensInitialize(void)
{
  unsigned int v0; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  _QWORD *v3; // rcx

  v0 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
  }
  if ( (unsigned int)Init() )
  {
    glpfnRasEnumConnections = 0;
    gIsRasInstalled = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
    }
    if ( (unsigned int)DoLanSetup() )
    {
      gbWSAInit = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
      }
      if ( (unsigned int)DoRpcSetup() )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
        }
        if ( (unsigned __int8)SensLogonInitialize() )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
              v3 = WPP_GLOBAL_Control;
            }
            if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 4u )
              WPP_SF_(v3[2], 20, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
          }
          goto LABEL_48;
        }
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_21:
          v0 = 0;
LABEL_48:
          CoUninitialize();
          return v0;
        }
        v2 = 18;
      }
      else
      {
        v1 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_21;
        }
        v2 = 16;
      }
    }
    else
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v2 = 14;
    }
    WPP_SF_(v1[2], v2, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180007ecc  mov     [rsp+arg_0], rbx
0x180007ed1  mov     [rsp+arg_8], rsi
0x180007ed6  push    rdi
0x180007ed7  sub     rsp, 20h
0x180007edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ee2  lea     rdi, WPP_GLOBAL_Control
0x180007ee9  lea     rsi, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x180007ef0  mov     ebx, 1
0x180007ef5  cmp     rcx, rdi
0x180007ef8  jz      short loc_180007F14
0x180007efa  test    [rcx+1Ch], bl
0x180007efd  jz      short loc_180007F14
0x180007eff  cmp     byte ptr [rcx+19h], 4
0x180007f03  jb      short loc_180007F14
0x180007f05  mov     rcx, [rcx+10h]
0x180007f09  lea     edx, [rbx+9]
0x180007f0c  mov     r8, rsi
0x180007f0f  call    WPP_SF_
0x180007f14  call    ?Init@@YAHXZ; Init(void)
0x180007f19  test    eax, eax
0x180007f1b  jnz     short loc_180007F4A
0x180007f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f24  cmp     rcx, rdi
0x180007f27  jz      short loc_180007F43
0x180007f29  test    [rcx+1Ch], bl
0x180007f2c  jz      short loc_180007F43
0x180007f2e  cmp     byte ptr [rcx+19h], 2
0x180007f32  jb      short loc_180007F43
0x180007f34  mov     rcx, [rcx+10h]
0x180007f38  lea     edx, [rax+0Bh]
0x180007f3b  mov     r8, rsi
0x180007f3e  call    WPP_SF_
0x180007f43  xor     ebx, ebx
0x180007f45  jmp     loc_1800080C4
0x180007f4a  mov     cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA, 0; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x180007f55  mov     cs:?gIsRasInstalled@@3W4SERVICE_INSTALL_STATE@@A, 0; SERVICE_INSTALL_STATE gIsRasInstalled
0x180007f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f66  cmp     rcx, rdi
0x180007f69  jz      short loc_180007F87
0x180007f6b  test    [rcx+1Ch], bl
0x180007f6e  jz      short loc_180007F87
0x180007f70  cmp     byte ptr [rcx+19h], 5
0x180007f74  jb      short loc_180007F87
0x180007f76  mov     rcx, [rcx+10h]
0x180007f7a  mov     edx, 0Dh
0x180007f7f  mov     r8, rsi
0x180007f82  call    WPP_SF_
0x180007f87  call    ?DoLanSetup@@YAHXZ; DoLanSetup(void)
0x180007f8c  test    eax, eax
0x180007f8e  jnz     short loc_180007FBD
0x180007f90  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f97  cmp     rcx, rdi
0x180007f9a  jz      short loc_180007FB6
0x180007f9c  test    [rcx+1Ch], bl
0x180007f9f  jz      short loc_180007FB6
0x180007fa1  cmp     byte ptr [rcx+19h], 2
0x180007fa5  jb      short loc_180007FB6
0x180007fa7  lea     edx, [rax+0Eh]
0x180007faa  mov     rcx, [rcx+10h]
0x180007fae  mov     r8, rsi
0x180007fb1  call    WPP_SF_
0x180007fb6  xor     ebx, ebx
0x180007fb8  jmp     loc_1800080BE
0x180007fbd  mov     cs:?gbWSAInit@@3_NA, bl; bool gbWSAInit
0x180007fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fca  cmp     rcx, rdi
0x180007fcd  jz      short loc_180007FEB
0x180007fcf  test    [rcx+1Ch], bl
0x180007fd2  jz      short loc_180007FEB
0x180007fd4  cmp     byte ptr [rcx+19h], 5
0x180007fd8  jb      short loc_180007FEB
0x180007fda  mov     rcx, [rcx+10h]
0x180007fde  mov     edx, 0Fh
0x180007fe3  mov     r8, rsi
0x180007fe6  call    WPP_SF_
0x180007feb  call    ?DoRpcSetup@@YAHXZ; DoRpcSetup(void)
0x180007ff0  test    eax, eax
0x180007ff2  jnz     short loc_180008010
0x180007ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ffb  cmp     rcx, rdi
0x180007ffe  jz      short loc_180007FB6
0x180008000  test    [rcx+1Ch], bl
0x180008003  jz      short loc_180007FB6
0x180008005  cmp     byte ptr [rcx+19h], 2
0x180008009  jb      short loc_180007FB6
0x18000800b  lea     edx, [rax+10h]
0x18000800e  jmp     short loc_180007FAA
0x180008010  mov     rcx, cs:WPP_GLOBAL_Control
0x180008017  cmp     rcx, rdi
0x18000801a  jz      short loc_180008038
0x18000801c  test    [rcx+1Ch], bl
0x18000801f  jz      short loc_180008038
0x180008021  cmp     byte ptr [rcx+19h], 5
0x180008025  jb      short loc_180008038
0x180008027  mov     rcx, [rcx+10h]
0x18000802b  mov     edx, 11h
0x180008030  mov     r8, rsi
0x180008033  call    WPP_SF_
0x180008038  call    SensLogonInitialize
0x18000803d  test    al, al
0x18000803f  jnz     short loc_18000806E
0x180008041  mov     rcx, cs:WPP_GLOBAL_Control
0x180008048  cmp     rcx, rdi
0x18000804b  jz      loc_180007FB6
0x180008051  test    [rcx+1Ch], bl
0x180008054  jz      loc_180007FB6
0x18000805a  cmp     byte ptr [rcx+19h], 2
0x18000805e  jb      loc_180007FB6
0x180008064  mov     edx, 12h
0x180008069  jmp     loc_180007FAA
0x18000806e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008075  cmp     rcx, rdi
0x180008078  jz      short loc_1800080BE
0x18000807a  test    [rcx+1Ch], bl
0x18000807d  jz      short loc_18000809D
0x18000807f  cmp     byte ptr [rcx+19h], 5
0x180008083  jb      short loc_18000809D
0x180008085  mov     rcx, [rcx+10h]
0x180008089  mov     edx, 13h
0x18000808e  mov     r8, rsi
0x180008091  call    WPP_SF_
0x180008096  mov     rcx, cs:WPP_GLOBAL_Control
0x18000809d  cmp     rcx, rdi
0x1800080a0  jz      short loc_1800080BE
0x1800080a2  test    [rcx+1Ch], bl
0x1800080a5  jz      short loc_1800080BE
0x1800080a7  cmp     byte ptr [rcx+19h], 4
0x1800080ab  jb      short loc_1800080BE
0x1800080ad  mov     rcx, [rcx+10h]
0x1800080b1  mov     edx, 14h
0x1800080b6  mov     r8, rsi
0x1800080b9  call    WPP_SF_
0x1800080be  call    cs:__imp_CoUninitialize
0x1800080c4  mov     rsi, [rsp+28h+arg_8]
0x1800080c9  mov     eax, ebx
0x1800080cb  mov     rbx, [rsp+28h+arg_0]
0x1800080d0  add     rsp, 20h
0x1800080d4  pop     rdi
0x1800080d5  retn
```
