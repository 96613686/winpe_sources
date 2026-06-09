# UvcFmtCreateHandler

- ea: `0x14000da90`
- end: `0x14000dd52`
- name: `UvcFmtCreateHandler`
- size: `706`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d7c0`
- `0x14001b014`
- `0x14001b094`

## callees

- `0x14000da90`
- `0x14000dd58`
- `0x14001b73c`
- `0x14001b760`
- `0x14003c4f4`
- `0x14003c518`
- `0x14003c53c`
- `0x14003c560`
- `0x14003c584`
- `0x14003c6f8`
- `0x14003c720`
- `0x14003c748`
- `0x14003c770`
- `0x14003c798`
- `0x14003c7c0`
- `0x14003c7e8`
- `0x140040a70`

## pseudocode

```c
__int64 __fastcall UvcFmtCreateHandler(char a1, _BYTE *a2, __int64 a3, _QWORD *a4)
{
  CFrameFormatPlugin *v5; // rax
  CFrameFormatPlugin *v6; // rax
  CFrameFormatPlugin *v7; // rbx
  unsigned int v8; // edx
  unsigned int v9; // edi
  __int64 result; // rax
  CStreamFormatPlugin *v11; // rax
  CStreamFormatPlugin *v12; // rax
  CStreamFormatPlugin *v13; // rbx
  unsigned int v14; // edx
  CDVFormatPlugin *v15; // rax
  CDVFormatPlugin *v16; // rax
  CDVFormatPlugin *v17; // rbx
  unsigned int v18; // edx
  CMJPEGFormatPlugin *v19; // rax
  CMJPEGFormatPlugin *v20; // rax
  CMJPEGFormatPlugin *v21; // rbx
  unsigned int v22; // edx
  CH264FormatPlugin *v23; // rax
  CH264FormatPlugin *v24; // rax
  CH264FormatPlugin *v25; // rbx
  unsigned int v26; // edx
  CUncompressedFormatPlugin *v27; // rax
  CUncompressedFormatPlugin *v28; // rax
  CUncompressedFormatPlugin *v29; // rbx
  unsigned int v30; // edx
  CMPEG2TSFormatPlugin *v31; // rax
  CMPEG2TSFormatPlugin *v32; // rax
  CMPEG2TSFormatPlugin *v33; // rbx
  unsigned int v34; // edx

  *a4 = 0;
  if ( a1 == 16 )
  {
LABEL_2:
    v5 = (CFrameFormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
    if ( v5 )
    {
      v6 = CFrameFormatPlugin::CFrameFormatPlugin(v5);
      v7 = v6;
      if ( v6 )
      {
        v9 = (**(__int64 (__fastcall ***)(CFrameFormatPlugin *, GUID *, _QWORD *))v6)(v6, &IID_IUnknown, a4);
        if ( v9 )
          CFrameFormatPlugin::`scalar deleting destructor'(v7, v8);
        return v9;
      }
    }
    return 3221225626LL;
  }
  if ( a1 == 18 )
  {
    v11 = (CStreamFormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
    if ( v11 )
    {
      v12 = CStreamFormatPlugin::CStreamFormatPlugin(v11);
      v13 = v12;
      if ( v12 )
      {
        v9 = (**(__int64 (__fastcall ***)(CStreamFormatPlugin *, GUID *, _QWORD *))v12)(v12, &IID_IUnknown, a4);
        if ( v9 )
          CStreamFormatPlugin::`scalar deleting destructor'(v13, v14);
        return v9;
      }
    }
    return 3221225626LL;
  }
  switch ( *a2 )
  {
    case 0xCC:
      v15 = (CDVFormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
      if ( v15 )
      {
        v16 = CDVFormatPlugin::CDVFormatPlugin(v15);
        v17 = v16;
        if ( v16 )
        {
          v9 = (**(__int64 (__fastcall ***)(CDVFormatPlugin *, GUID *, _QWORD *))v16)(v16, &IID_IUnknown, a4);
          if ( v9 )
            CDVFormatPlugin::`scalar deleting destructor'(v17, v18);
          return v9;
        }
      }
      return 3221225626LL;
    case 0xC6:
      v19 = (CMJPEGFormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
      if ( v19 )
      {
        v20 = CMJPEGFormatPlugin::CMJPEGFormatPlugin(v19);
        v21 = v20;
        if ( v20 )
        {
          v9 = (**(__int64 (__fastcall ***)(CMJPEGFormatPlugin *, GUID *, _QWORD *))v20)(v20, &IID_IUnknown, a4);
          if ( v9 )
            CMJPEGFormatPlugin::`scalar deleting destructor'(v21, v22);
          return v9;
        }
      }
      return 3221225626LL;
    case 0xD3:
      v23 = (CH264FormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
      if ( v23 )
      {
        v24 = CH264FormatPlugin::CH264FormatPlugin(v23);
        v25 = v24;
        if ( v24 )
        {
          v9 = (**(__int64 (__fastcall ***)(CH264FormatPlugin *, GUID *, _QWORD *))v24)(v24, &IID_IUnknown, a4);
          if ( v9 )
            CH264FormatPlugin::`scalar deleting destructor'(v25, v26);
          return v9;
        }
      }
      return 3221225626LL;
    case 0xC4:
      v27 = (CUncompressedFormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
      if ( v27 )
      {
        v28 = CUncompressedFormatPlugin::CUncompressedFormatPlugin(v27);
        v29 = v28;
        if ( v28 )
        {
          v9 = (**(__int64 (__fastcall ***)(CUncompressedFormatPlugin *, GUID *, _QWORD *))v28)(v28, &IID_IUnknown, a4);
          if ( v9 )
            CUncompressedFormatPlugin::`scalar deleting destructor'(v29, v30);
          return v9;
        }
      }
      return 3221225626LL;
    case 0xD0:
      goto LABEL_2;
    case 0xCA:
      v31 = (CMPEG2TSFormatPlugin *)operator new(0x20u, (enum _POOL_TYPE)a2);
      if ( v31 )
      {
        v32 = CMPEG2TSFormatPlugin::CMPEG2TSFormatPlugin(v31);
        v33 = v32;
        if ( v32 )
        {
          v9 = (**(__int64 (__fastcall ***)(CMPEG2TSFormatPlugin *, GUID *, _QWORD *))v32)(v32, &IID_IUnknown, a4);
          if ( v9 )
            CMPEG2TSFormatPlugin::`scalar deleting destructor'(v33, v34);
          return v9;
        }
      }
      return 3221225626LL;
  }
  if ( ((*a2 + 56) & 0xFC) == 0 && *a2 != 0xCA )
    return 3221225474LL;
  result = 3221225524LL;
  if ( *a2 == 0xCE )
    return 3221225474LL;
  return result;
}

```

## disassembly

```asm
0x14000da90  mov     [rsp+arg_0], rbx
0x14000da95  push    rdi
0x14000da96  sub     rsp, 20h
0x14000da9a  mov     qword ptr [r9], 0
0x14000daa1  mov     rdi, r9
0x14000daa4  cmp     cl, 10h
0x14000daa7  jnz     short loc_14000DAFD
0x14000daa9  mov     ecx, 20h ; ' '; Size
0x14000daae  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000dab3  test    rax, rax
0x14000dab6  jz      loc_14000DD1E
0x14000dabc  mov     rcx, rax; this
0x14000dabf  call    ??0CFrameFormatPlugin@@QEAA@XZ; CFrameFormatPlugin::CFrameFormatPlugin(void)
0x14000dac4  mov     rbx, rax
0x14000dac7  test    rax, rax
0x14000daca  jz      loc_14000DD1E
0x14000dad0  mov     rcx, [rax]
0x14000dad3  lea     rdx, IID_IUnknown
0x14000dada  mov     r8, rdi
0x14000dadd  mov     rax, [rcx]
0x14000dae0  mov     rcx, rbx
0x14000dae3  call    _guard_dispatch_icall
0x14000dae8  mov     edi, eax
0x14000daea  test    eax, eax
0x14000daec  jz      short loc_14000DAF6
0x14000daee  mov     rcx, rbx; this
0x14000daf1  call    ??_GCFrameFormatPlugin@@QEAAPEAXI@Z; CFrameFormatPlugin::`scalar deleting destructor'(uint)
0x14000daf6  mov     eax, edi
0x14000daf8  jmp     loc_14000DD46
0x14000dafd  cmp     cl, 12h
0x14000db00  jnz     short loc_14000DB51
0x14000db02  mov     ecx, 20h ; ' '; Size
0x14000db07  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000db0c  test    rax, rax
0x14000db0f  jz      loc_14000DD1E
0x14000db15  mov     rcx, rax; this
0x14000db18  call    ??0CStreamFormatPlugin@@QEAA@XZ; CStreamFormatPlugin::CStreamFormatPlugin(void)
0x14000db1d  mov     rbx, rax
0x14000db20  test    rax, rax
0x14000db23  jz      loc_14000DD1E
0x14000db29  mov     rcx, [rax]
0x14000db2c  lea     rdx, IID_IUnknown
0x14000db33  mov     r8, rdi
0x14000db36  mov     rax, [rcx]
0x14000db39  mov     rcx, rbx
0x14000db3c  call    _guard_dispatch_icall
0x14000db41  mov     edi, eax
0x14000db43  test    eax, eax
0x14000db45  jz      short loc_14000DAF6
0x14000db47  mov     rcx, rbx; this
0x14000db4a  call    ??_GCStreamFormatPlugin@@QEAAPEAXI@Z; CStreamFormatPlugin::`scalar deleting destructor'(uint)
0x14000db4f  jmp     short loc_14000DAF6
0x14000db51  mov     al, [rdx]
0x14000db53  add     al, 40h ; '@'
0x14000db55  mov     cl, al
0x14000db57  cmp     al, 0Ch
0x14000db59  jnz     short loc_14000DBB1
0x14000db5b  mov     ecx, 20h ; ' '; Size
0x14000db60  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000db65  test    rax, rax
0x14000db68  jz      loc_14000DD1E
0x14000db6e  mov     rcx, rax; this
0x14000db71  call    ??0CDVFormatPlugin@@QEAA@XZ; CDVFormatPlugin::CDVFormatPlugin(void)
0x14000db76  mov     rbx, rax
0x14000db79  test    rax, rax
0x14000db7c  jz      loc_14000DD1E
0x14000db82  mov     rcx, [rax]
0x14000db85  lea     rdx, IID_IUnknown
0x14000db8c  mov     r8, rdi
0x14000db8f  mov     rax, [rcx]
0x14000db92  mov     rcx, rbx
0x14000db95  call    _guard_dispatch_icall
0x14000db9a  mov     edi, eax
0x14000db9c  test    eax, eax
0x14000db9e  jz      loc_14000DAF6
0x14000dba4  mov     rcx, rbx; this
0x14000dba7  call    ??_GCDVFormatPlugin@@QEAAPEAXI@Z; CDVFormatPlugin::`scalar deleting destructor'(uint)
0x14000dbac  jmp     loc_14000DAF6
0x14000dbb1  cmp     cl, 6
0x14000dbb4  jnz     short loc_14000DC0C
0x14000dbb6  mov     ecx, 20h ; ' '; Size
0x14000dbbb  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000dbc0  test    rax, rax
0x14000dbc3  jz      loc_14000DD1E
0x14000dbc9  mov     rcx, rax; this
0x14000dbcc  call    ??0CMJPEGFormatPlugin@@QEAA@XZ; CMJPEGFormatPlugin::CMJPEGFormatPlugin(void)
0x14000dbd1  mov     rbx, rax
0x14000dbd4  test    rax, rax
0x14000dbd7  jz      loc_14000DD1E
0x14000dbdd  mov     rcx, [rax]
0x14000dbe0  lea     rdx, IID_IUnknown
0x14000dbe7  mov     r8, rdi
0x14000dbea  mov     rax, [rcx]
0x14000dbed  mov     rcx, rbx
0x14000dbf0  call    _guard_dispatch_icall
0x14000dbf5  mov     edi, eax
0x14000dbf7  test    eax, eax
0x14000dbf9  jz      loc_14000DAF6
0x14000dbff  mov     rcx, rbx; this
0x14000dc02  call    ??_GCMJPEGFormatPlugin@@QEAAPEAXI@Z; CMJPEGFormatPlugin::`scalar deleting destructor'(uint)
0x14000dc07  jmp     loc_14000DAF6
0x14000dc0c  cmp     cl, 13h
0x14000dc0f  jnz     short loc_14000DC67
0x14000dc11  mov     ecx, 20h ; ' '; Size
0x14000dc16  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000dc1b  test    rax, rax
0x14000dc1e  jz      loc_14000DD1E
0x14000dc24  mov     rcx, rax; this
0x14000dc27  call    ??0CH264FormatPlugin@@QEAA@XZ; CH264FormatPlugin::CH264FormatPlugin(void)
0x14000dc2c  mov     rbx, rax
0x14000dc2f  test    rax, rax
0x14000dc32  jz      loc_14000DD1E
0x14000dc38  mov     rcx, [rax]
0x14000dc3b  lea     rdx, IID_IUnknown
0x14000dc42  mov     r8, rdi
0x14000dc45  mov     rax, [rcx]
0x14000dc48  mov     rcx, rbx
0x14000dc4b  call    _guard_dispatch_icall
0x14000dc50  mov     edi, eax
0x14000dc52  test    eax, eax
0x14000dc54  jz      loc_14000DAF6
0x14000dc5a  mov     rcx, rbx; this
0x14000dc5d  call    ??_GCH264FormatPlugin@@QEAAPEAXI@Z; CH264FormatPlugin::`scalar deleting destructor'(uint)
0x14000dc62  jmp     loc_14000DAF6
0x14000dc67  cmp     cl, 4
0x14000dc6a  jnz     short loc_14000DCC2
0x14000dc6c  mov     ecx, 20h ; ' '; Size
0x14000dc71  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000dc76  test    rax, rax
0x14000dc79  jz      loc_14000DD1E
0x14000dc7f  mov     rcx, rax; this
0x14000dc82  call    ??0CUncompressedFormatPlugin@@QEAA@XZ; CUncompressedFormatPlugin::CUncompressedFormatPlugin(void)
0x14000dc87  mov     rbx, rax
0x14000dc8a  test    rax, rax
0x14000dc8d  jz      loc_14000DD1E
0x14000dc93  mov     rcx, [rax]
0x14000dc96  lea     rdx, IID_IUnknown
0x14000dc9d  mov     r8, rdi
0x14000dca0  mov     rax, [rcx]
0x14000dca3  mov     rcx, rbx
0x14000dca6  call    _guard_dispatch_icall
0x14000dcab  mov     edi, eax
0x14000dcad  test    eax, eax
0x14000dcaf  jz      loc_14000DAF6
0x14000dcb5  mov     rcx, rbx; this
0x14000dcb8  call    ??_GCUncompressedFormatPlugin@@QEAAPEAXI@Z; CUncompressedFormatPlugin::`scalar deleting destructor'(uint)
0x14000dcbd  jmp     loc_14000DAF6
0x14000dcc2  cmp     cl, 10h
0x14000dcc5  jz      loc_14000DAA9
0x14000dccb  cmp     cl, 0Ah
0x14000dcce  jnz     short loc_14000DD25
0x14000dcd0  mov     ecx, 20h ; ' '; Size
0x14000dcd5  call    ??2@YAPEAX_KW4_POOL_TYPE@@@Z; operator new(unsigned __int64,_POOL_TYPE)
0x14000dcda  test    rax, rax
0x14000dcdd  jz      short loc_14000DD1E
0x14000dcdf  mov     rcx, rax; this
0x14000dce2  call    ??0CMPEG2TSFormatPlugin@@QEAA@XZ; CMPEG2TSFormatPlugin::CMPEG2TSFormatPlugin(void)
0x14000dce7  mov     rbx, rax
0x14000dcea  test    rax, rax
0x14000dced  jz      short loc_14000DD1E
0x14000dcef  mov     rcx, [rax]
0x14000dcf2  lea     rdx, IID_IUnknown
0x14000dcf9  mov     r8, rdi
0x14000dcfc  mov     rax, [rcx]
0x14000dcff  mov     rcx, rbx
0x14000dd02  call    _guard_dispatch_icall
0x14000dd07  mov     edi, eax
0x14000dd09  test    eax, eax
0x14000dd0b  jz      loc_14000DAF6
0x14000dd11  mov     rcx, rbx; this
0x14000dd14  call    ??_GCMPEG2TSFormatPlugin@@QEAAPEAXI@Z; CMPEG2TSFormatPlugin::`scalar deleting destructor'(uint)
0x14000dd19  jmp     loc_14000DAF6
0x14000dd1e  mov     eax, 0C000009Ah
0x14000dd23  jmp     short loc_14000DD46
0x14000dd25  lea     eax, [rcx-8]
0x14000dd28  test    al, 0FCh
0x14000dd2a  jnz     short loc_14000DD38
0x14000dd2c  cmp     cl, 0Ah
0x14000dd2f  jz      short loc_14000DD38
0x14000dd31  mov     eax, 0C0000002h
0x14000dd36  jmp     short loc_14000DD46
0x14000dd38  mov     eax, 0C0000034h
0x14000dd3d  cmp     cl, 0Eh
0x14000dd40  lea     edx, [rax-32h]
0x14000dd43  cmovz   eax, edx
0x14000dd46  mov     rbx, [rsp+28h+arg_0]
0x14000dd4b  add     rsp, 20h
0x14000dd4f  pop     rdi
0x14000dd50  retn
```
