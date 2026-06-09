# CWMIBinMof::DeleteMofsFromEvent(CVARIANT &,CVARIANT &,int &)

- ea: `0x180017e3c`
- end: `0x180017fd1`
- name: `?DeleteMofsFromEvent@CWMIBinMof@@QEAAJAEAVCVARIANT@@0AEAH@Z`
- size: `405`
- prototype: `__int64 __fastcall(CWMIBinMof *__hidden this, struct CVARIANT *, struct CVARIANT *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180001680`

## callees

- `0x1800021f0`
- `0x180002ea4`
- `0x180003b08`
- `0x1800079f0`
- `0x18000ca3c`
- `0x1800172fc`
- `0x180017460`
- `0x180017e3c`
- `0x180017fd8`
- `0x1800187d4`
- `0x1800193b4`

## pseudocode

```c
__int64 __fastcall CWMIBinMof::DeleteMofsFromEvent(CWMIBinMof *this, struct CVARIANT *a2, struct CVARIANT *a3, int *a4)
{
  int inited; // ebx
  __int64 v9; // rax
  __int64 v10; // r8
  int v11; // eax
  CWMIBinMof *v12; // rcx
  __int64 v13; // rax
  const unsigned __int16 *v14; // rdx
  int v15; // edx
  unsigned __int16 *v17; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v18[136]; // [rsp+40h] [rbp-88h] BYREF

  CAutoWChar::CAutoWChar((CAutoWChar *)&v17, 520);
  if ( !v17 )
  {
    inited = -2147217402;
    goto LABEL_24;
  }
  inited = -2147217393;
  *a4 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( *(_WORD *)a3 != 1 && *((_QWORD *)a3 + 1) )
    {
      if ( *(_WORD *)a2 == 1 )
      {
        v13 = CVARIANT::operator unsigned short *(a3);
        v11 = StringCchPrintfW(v17, 0x208u, L"%s-%s", v13, L"{05901221-D566-11d1-B2F0-00A0C9062910}");
LABEL_10:
        inited = v11;
        if ( v11 >= 0 )
        {
          if ( *(_DWORD *)this )
          {
            CNamespaceManagement::CNamespaceManagement((CNamespaceManagement *)v18, this);
            inited = CNamespaceManagement::InitQuery(
                       (CNamespaceManagement *)v18,
                       L"select * from WMIBinaryMofResource where Name = ");
            if ( inited >= 0 )
            {
              inited = CNamespaceManagement::UpdateQuery((CNamespaceManagement *)v18, v14, v17);
              if ( inited >= 0 )
              {
                if ( (unsigned int)CNamespaceManagement::DeleteOldDrivers((const OLECHAR **)v18, v15) )
                {
                  inited = 0;
                  *a4 = 1;
                }
              }
            }
            CNamespaceManagement::~CNamespaceManagement((CNamespaceManagement *)v18);
          }
          else
          {
            if ( ((int (__stdcall *)(CWMIBinMof *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, int))CWMIBinMof::ThisMofExistsInRegistry)(
                   v12,
                   L"Software\\Microsoft\\WBEM\\WDM",
                   v17,
                   0,
                   0,
                   0) )
            {
              *a4 = 1;
            }
            inited = 0;
          }
        }
        goto LABEL_24;
      }
      if ( *((_QWORD *)a2 + 1) )
      {
        CVARIANT::operator unsigned short *(a3);
        v9 = CVARIANT::operator unsigned short *(a2);
        v11 = StringCchPrintfW(v17, 0x208u, L"%s[%s]", v9, v10);
        goto LABEL_10;
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &CHeap_Exception `RTTI Type Descriptor', 0) )
    {
      inited = -2147217402;
      __eh34_try_continuation(0, &CHeap_Exception `RTTI Type Descriptor', &loc_180017FB1);
    }
  }
LABEL_24:
  CAutoWChar::~CAutoWChar((void **)&v17);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180017e3c  push    rbx
0x180017e3e  push    rsi
0x180017e3f  push    r12
0x180017e41  push    r14
0x180017e43  push    r15
0x180017e45  sub     rsp, 0A0h
0x180017e4c  mov     rsi, r9
0x180017e4f  mov     r14, r8
0x180017e52  mov     r15, rdx
0x180017e55  mov     r12, rcx
0x180017e58  mov     edx, 208h; int
0x180017e5d  lea     rcx, [rsp+0C8h+var_90]; this
0x180017e62  call    ??0CAutoWChar@@QEAA@H@Z; CAutoWChar::CAutoWChar(int)
0x180017e67  nop
0x180017e68  cmp     [rsp+0C8h+var_90], 0
0x180017e6e  jnz     short loc_180017E7A
0x180017e70  mov     ebx, 80041006h
0x180017e75  jmp     loc_180017FB5
0x180017e7a  mov     ebx, 8004100Fh
0x180017e7f  mov     dword ptr [rsi], 0
0x180017e85  mov     eax, 1
0x180017e8a  cmp     [r14], ax
0x180017e8e  jz      loc_180017FAF
0x180017e94  cmp     qword ptr [r14+8], 0
0x180017e99  jz      loc_180017FAF
0x180017e9f  cmp     [r15], ax
0x180017ea3  jz      short loc_180017ED1
0x180017ea5  cmp     qword ptr [r15+8], 0
0x180017eaa  jz      loc_180017FAF
0x180017eb0  mov     rcx, r14
0x180017eb3  call    ??BCVARIANT@@QEAAPEAGXZ; CVARIANT::operator ushort *(void)
0x180017eb8  mov     r8, rax
0x180017ebb  mov     rcx, r15
0x180017ebe  call    ??BCVARIANT@@QEAAPEAGXZ; CVARIANT::operator ushort *(void)
0x180017ec3  mov     qword ptr [rsp+0C8h+var_A8], r8
0x180017ec8  lea     r8, aSS_1; "%s[%s]"
0x180017ecf  jmp     short loc_180017EEC
0x180017ed1  mov     rcx, r14
0x180017ed4  call    ??BCVARIANT@@QEAAPEAGXZ; CVARIANT::operator ushort *(void)
0x180017ed9  lea     rcx, a05901221D56611; "{05901221-D566-11d1-B2F0-00A0C9062910}"
0x180017ee0  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x180017ee5  lea     r8, aSS; "%s-%s"
0x180017eec  mov     r9, rax
0x180017eef  mov     edx, 208h; unsigned __int64
0x180017ef4  mov     rcx, [rsp+0C8h+var_90]; unsigned __int16 *
0x180017ef9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017efe  mov     [rsp+0C8h+var_98], eax
0x180017f02  mov     ebx, eax
0x180017f04  test    eax, eax
0x180017f06  js      loc_180017FAF
0x180017f0c  cmp     dword ptr [r12], 0
0x180017f11  jz      short loc_180017F7B
0x180017f13  mov     rdx, r12; struct CWMIBinMof *
0x180017f16  lea     rcx, [rsp+0C8h+var_88]; this
0x180017f1b  call    ??0CNamespaceManagement@@QEAA@PEAVCWMIBinMof@@@Z; CNamespaceManagement::CNamespaceManagement(CWMIBinMof *)
0x180017f20  nop
0x180017f21  lea     rdx, aSelectFromWmib_1; "select * from WMIBinaryMofResource wher"...
0x180017f28  lea     rcx, [rsp+0C8h+var_88]; this
0x180017f2d  call    ?InitQuery@CNamespaceManagement@@QEAAJPEBG@Z; CNamespaceManagement::InitQuery(ushort const *)
0x180017f32  mov     ebx, eax
0x180017f34  mov     [rsp+0C8h+var_98], eax
0x180017f38  test    eax, eax
0x180017f3a  js      short loc_180017F6F
0x180017f3c  mov     r8, [rsp+0C8h+var_90]; unsigned __int16 *
0x180017f41  lea     rcx, [rsp+0C8h+var_88]; this
0x180017f46  call    ?UpdateQuery@CNamespaceManagement@@QEAAJPEBG0@Z; CNamespaceManagement::UpdateQuery(ushort const *,ushort const *)
0x180017f4b  mov     ebx, eax
0x180017f4d  mov     [rsp+0C8h+var_98], eax
0x180017f51  test    eax, eax
0x180017f53  js      short loc_180017F6F
0x180017f55  lea     rcx, [rsp+0C8h+var_88]; this
0x180017f5a  call    ?DeleteOldDrivers@CNamespaceManagement@@QEAAHH@Z; CNamespaceManagement::DeleteOldDrivers(int)
0x180017f5f  test    eax, eax
0x180017f61  jz      short loc_180017F6F
0x180017f63  xor     ebx, ebx
0x180017f65  mov     [rsp+0C8h+var_98], ebx
0x180017f69  mov     dword ptr [rsi], 1
0x180017f6f  lea     rcx, [rsp+0C8h+var_88]; this
0x180017f74  call    ??1CNamespaceManagement@@QEAA@XZ; CNamespaceManagement::~CNamespaceManagement(void)
0x180017f79  jmp     short loc_180017FAF
0x180017f7b  mov     [rsp+0C8h+var_A0], 0; int
0x180017f83  mov     [rsp+0C8h+var_A8], 0; unsigned int
0x180017f8b  xor     r9d, r9d; unsigned int
0x180017f8e  mov     r8, [rsp+0C8h+var_90]; unsigned __int16 *
0x180017f93  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WBEM\\WDM"
0x180017f9a  call    ?ThisMofExistsInRegistry@CWMIBinMof@@QEAAHPEAG0KKH@Z; CWMIBinMof::ThisMofExistsInRegistry(ushort *,ushort *,ulong,ulong,int)
0x180017f9f  test    eax, eax
0x180017fa1  jz      short loc_180017FA9
0x180017fa3  mov     dword ptr [rsi], 1
0x180017fa9  xor     ebx, ebx
0x180017fab  mov     [rsp+0C8h+var_98], ebx
0x180017faf  jmp     short loc_180017FB5
0x180017fb1  mov     ebx, [rsp+0C8h+var_98]
0x180017fb5  lea     rcx, [rsp+0C8h+var_90]; this
0x180017fba  call    ??1CAutoWChar@@QEAA@XZ; CAutoWChar::~CAutoWChar(void)
0x180017fbf  mov     eax, ebx
0x180017fc1  add     rsp, 0A0h
0x180017fc8  pop     r15
0x180017fca  pop     r14
0x180017fcc  pop     r12
0x180017fce  pop     rsi
0x180017fcf  pop     rbx
0x180017fd0  retn
```
