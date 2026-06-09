# ParseLock(IHttpContext *,IXmlReader *,DAV_LOCK_REQUEST *)

- ea: `0x180012c54`
- end: `0x180013076`
- name: `?ParseLock@@YAJPEAVIHttpContext@@PEAUIXmlReader@@PEAVDAV_LOCK_REQUEST@@@Z`
- size: `1058`
- prototype: `__int64 __fastcall(struct IHttpContext *, struct IXmlReader *, struct DAV_LOCK_REQUEST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18000bc4c`

## callees

- `0x180012c54`
- `0x18001307c`
- `0x18001e184`
- `0x18001e6a4`
- `0x18001e898`
- `0x18001e998`
- `0x18001ea6c`
- `0x1800224e6`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012f32`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180012f32`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012ca8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012cb3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012ef8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012ca8`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012cb3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180012ef8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012f46`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012fbf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012fc9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012f46`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012fbf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180012fc9`

## string_xrefs

- `0x180012dc5`: `write`
- `0x180013006`: `write`
- `0x180012f9c`: `LOCK: Required XML Elements Missing`
- `0x18001300d`: `Unexpected XML Element`

## pseudocode

```c
__int64 __fastcall ParseLock(struct IHttpContext *a1, struct IXmlReader *a2, struct DAV_LOCK_REQUEST *a3)
{
  _WORD *v6; // rcx
  const unsigned __int16 *v7; // rdx
  int NodeByType; // ebx
  int v9; // r15d
  int i; // eax
  wchar_t *v11; // rbx
  int j; // eax
  int k; // eax
  const unsigned __int16 *v14; // r8
  __int64 v15; // rax
  const wchar_t *v16; // r8
  const wchar_t *v17; // rdx
  wchar_t *v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-C0h] BYREF
  int v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v25[32]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  _BYTE v27[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v28; // [rsp+B0h] [rbp-50h]
  _BYTE v29[32]; // [rsp+C8h] [rbp-38h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp-18h]

  v24 = 0;
  v20 = 0;
  String1 = 0;
  v19 = 0;
  STRU::STRU((STRU *)v27);
  STRU::STRU((STRU *)v25);
  *((_DWORD *)a3 + 16) = 0;
  *((_DWORD *)a3 + 14) = -1;
  *((_DWORD *)a3 + 15) = -1;
  v6 = (_WORD *)*((_QWORD *)a3 + 4);
  v22 = 0;
  v23 = 0;
  *v6 = 0;
  *((_DWORD *)a3 + 12) = 0;
  NodeByType = XmlFindNodeByType(a2, XmlNodeType_Element);
  if ( NodeByType >= 0 )
  {
    NodeByType = XmlCheckNodeName(a2, v7, L"lockinfo");
    if ( NodeByType >= 0 )
    {
      NodeByType = XmlFindLanguageTag(a2, (struct STRU *)v27, &v23);
      if ( NodeByType >= 0 )
      {
        v9 = 0;
        for ( i = XmlFindFirstSubElement(a2, &v24, (const unsigned __int16 **)&String1, (const unsigned __int16 **)&v19);
              ;
              i = XmlFindNextSubElement(a2, v24, (const unsigned __int16 **)&String1, (const unsigned __int16 **)&v19) )
        {
          NodeByType = i;
          if ( i == 1 )
            break;
          if ( i < 0 )
            goto LABEL_47;
          if ( !wcscmp_0(String1, L"DAV:") )
          {
            v11 = v19;
            if ( !wcscmp_0(v19, L"locktype") )
            {
              for ( j = XmlFindFirstSubElement(
                          a2,
                          &v20,
                          (const unsigned __int16 **)&String1,
                          (const unsigned __int16 **)&v19);
                    ;
                    j = XmlFindNextSubElement(
                          a2,
                          v20,
                          (const unsigned __int16 **)&String1,
                          (const unsigned __int16 **)&v19) )
              {
                NodeByType = j;
                if ( j == 1 )
                  break;
                if ( j < 0 )
                  goto LABEL_47;
                if ( !wcscmp_0(String1, L"DAV:") && !wcscmp_0(v19, L"write") )
                {
                  if ( *((_DWORD *)a3 + 14) != -1 )
                  {
                    NodeByType = -2147024809;
                    v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
                    v16 = L"write";
                    goto LABEL_49;
                  }
                  *((_DWORD *)a3 + 14) = 0;
                }
              }
            }
            else if ( !wcscmp_0(v11, L"lockscope") )
            {
              for ( k = XmlFindFirstSubElement(
                          a2,
                          &v20,
                          (const unsigned __int16 **)&String1,
                          (const unsigned __int16 **)&v19);
                    ;
                    k = XmlFindNextSubElement(
                          a2,
                          v20,
                          (const unsigned __int16 **)&String1,
                          (const unsigned __int16 **)&v19) )
              {
                NodeByType = k;
                if ( k == 1 )
                  break;
                if ( k < 0 )
                  goto LABEL_47;
                if ( !wcscmp_0(String1, L"DAV:") )
                {
                  if ( !wcscmp_0(v19, L"exclusive") )
                  {
                    if ( *((_DWORD *)a3 + 15) != -1 )
                    {
                      NodeByType = -2147024809;
                      v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
                      v16 = L"exclusive";
                      goto LABEL_49;
                    }
                    *((_DWORD *)a3 + 15) = 0;
                  }
                  if ( !wcscmp_0(v19, L"shared") )
                  {
                    if ( *((_DWORD *)a3 + 15) != -1 )
                    {
                      NodeByType = -2147024809;
                      v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
                      v16 = L"shared";
                      goto LABEL_49;
                    }
                    *((_DWORD *)a3 + 15) = 1;
                  }
                }
              }
            }
            else if ( !wcscmp_0(v11, L"owner") )
            {
              if ( v9 )
              {
                NodeByType = -2147024809;
                v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
                v16 = L"owner";
LABEL_49:
                v17 = L"Unexpected XML Element";
                goto LABEL_46;
              }
              NodeByType = XmlFindLanguageTag(a2, (struct STRU *)v25, &v22);
              if ( NodeByType < 0 )
                goto LABEL_47;
              STRU::STRU((STRU *)v29);
              v14 = (const unsigned __int16 *)(v22 ? v26 : v28 & -(__int64)(v23 != 0));
              NodeByType = ParseOwnerElement(a2, (struct STRU *)v29, v14);
              if ( NodeByType >= 0 )
              {
                NodeByType = STRU::Copy(a3, v30);
                if ( NodeByType >= 0 )
                  *((_DWORD *)a3 + 16) = 1;
              }
              STRU::~STRU((STRU *)v29);
              if ( NodeByType < 0 )
                goto LABEL_47;
              v9 = 1;
            }
          }
        }
        if ( *((_DWORD *)a3 + 14) == -1 || (NodeByType = 0, *((_DWORD *)a3 + 15) == -1) )
        {
          NodeByType = -2147024809;
          v15 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a1 + 272LL))(a1);
          v16 = 0;
          v17 = L"LOCK: Required XML Elements Missing";
LABEL_46:
          (*(void (__fastcall **)(__int64, const wchar_t *, const wchar_t *, _QWORD, char))(*(_QWORD *)v15 + 32LL))(
            v15,
            v17,
            v16,
            0,
            3);
        }
      }
    }
  }
LABEL_47:
  STRU::~STRU((STRU *)v25);
  STRU::~STRU((STRU *)v27);
  return (unsigned int)NodeByType;
}

```

## disassembly

```asm
0x180012c54  push    rbp
0x180012c56  push    rbx
0x180012c57  push    rsi
0x180012c58  push    rdi
0x180012c59  push    r13
0x180012c5b  push    r14
0x180012c5d  push    r15
0x180012c5f  lea     rbp, [rsp-10h]
0x180012c64  sub     rsp, 110h
0x180012c6b  mov     rax, cs:__security_cookie
0x180012c72  xor     rax, rsp
0x180012c75  mov     [rbp+40h+var_40], rax
0x180012c79  mov     r14, rcx
0x180012c7c  mov     [rsp+140h+var_F0], 0
0x180012c84  lea     rcx, [rbp+40h+var_B0]
0x180012c88  mov     [rsp+140h+var_108], 0
0x180012c90  mov     rdi, r8
0x180012c93  mov     [rsp+140h+String1], 0
0x180012c9c  mov     rsi, rdx
0x180012c9f  mov     [rsp+140h+var_110], 0
0x180012ca8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012cae  lea     rcx, [rsp+140h+var_E8]
0x180012cb3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012cb9  or      eax, 0FFFFFFFFh
0x180012cbc  mov     dword ptr [rdi+40h], 0
0x180012cc3  mov     [rdi+38h], eax
0x180012cc6  mov     [rdi+3Ch], eax
0x180012cc9  xor     eax, eax
0x180012ccb  mov     rcx, [rdi+20h]
0x180012ccf  mov     [rsp+140h+var_F8], 0
0x180012cd7  mov     [rsp+140h+var_F4], 0
0x180012cdf  lea     r13d, [rax+1]
0x180012ce3  mov     [rcx], ax
0x180012ce6  mov     edx, r13d; enum XmlNodeType
0x180012ce9  mov     rcx, rsi; struct IXmlReader *
0x180012cec  mov     [rdi+30h], eax
0x180012cef  call    ?XmlFindNodeByType@@YAJPEAUIXmlReader@@W4XmlNodeType@@@Z; XmlFindNodeByType(IXmlReader *,XmlNodeType)
0x180012cf4  mov     ebx, eax
0x180012cf6  test    eax, eax
0x180012cf8  js      loc_180012FBA
0x180012cfe  lea     r8, aLockinfo; "lockinfo"
0x180012d05  mov     rcx, rsi; struct IXmlReader *
0x180012d08  call    ?XmlCheckNodeName@@YAJPEAUIXmlReader@@PEBG1@Z; XmlCheckNodeName(IXmlReader *,ushort const *,ushort const *)
0x180012d0d  mov     ebx, eax
0x180012d0f  test    eax, eax
0x180012d11  js      loc_180012FBA
0x180012d17  lea     r8, [rsp+140h+var_F4]; int *
0x180012d1c  mov     rcx, rsi; struct IXmlReader *
0x180012d1f  lea     rdx, [rbp+40h+var_B0]; struct STRU *
0x180012d23  call    ?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z; XmlFindLanguageTag(IXmlReader *,STRU *,int *)
0x180012d28  mov     ebx, eax
0x180012d2a  test    eax, eax
0x180012d2c  js      loc_180012FBA
0x180012d32  xor     r15d, r15d
0x180012d35  lea     r9, [rsp+140h+var_110]; unsigned __int16 **
0x180012d3a  lea     r8, [rsp+140h+String1]; unsigned __int16 **
0x180012d3f  mov     rcx, rsi; struct IXmlReader *
0x180012d42  lea     rdx, [rsp+140h+var_F0]; unsigned int *
0x180012d47  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x180012d4c  jmp     loc_180012F69
0x180012d51  test    ebx, ebx
0x180012d53  js      loc_180012FBA
0x180012d59  mov     rcx, [rsp+140h+String1]; String1
0x180012d5e  lea     rdx, aDav; "DAV:"
0x180012d65  call    wcscmp_0
0x180012d6a  test    eax, eax
0x180012d6c  jnz     loc_180012F53
0x180012d72  mov     rbx, [rsp+140h+var_110]
0x180012d77  lea     rdx, aLocktype; "locktype"
0x180012d7e  mov     rcx, rbx; String1
0x180012d81  call    wcscmp_0
0x180012d86  test    eax, eax
0x180012d88  jnz     short loc_180012E04
0x180012d8a  lea     r9, [rsp+140h+var_110]; unsigned __int16 **
0x180012d8f  mov     rcx, rsi; struct IXmlReader *
0x180012d92  lea     r8, [rsp+140h+String1]; unsigned __int16 **
0x180012d97  lea     rdx, [rsp+140h+var_108]; unsigned int *
0x180012d9c  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x180012da1  jmp     short loc_180012DF8
0x180012da3  test    ebx, ebx
0x180012da5  js      loc_180012FBA
0x180012dab  mov     rcx, [rsp+140h+String1]; String1
0x180012db0  lea     rdx, aDav; "DAV:"
0x180012db7  call    wcscmp_0
0x180012dbc  test    eax, eax
0x180012dbe  jnz     short loc_180012DE2
0x180012dc0  mov     rcx, [rsp+140h+var_110]; String1
0x180012dc5  lea     rdx, aWrite; "write"
0x180012dcc  call    wcscmp_0
0x180012dd1  test    eax, eax
0x180012dd3  jnz     short loc_180012DE2
0x180012dd5  cmp     dword ptr [rdi+38h], 0FFFFFFFFh
0x180012dd9  jnz     loc_180012FEF
0x180012ddf  mov     [rdi+38h], eax
0x180012de2  mov     edx, [rsp+140h+var_108]; unsigned int
0x180012de6  lea     r9, [rsp+140h+var_110]; unsigned __int16 **
0x180012deb  lea     r8, [rsp+140h+String1]; unsigned __int16 **
0x180012df0  mov     rcx, rsi; struct IXmlReader *
0x180012df3  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x180012df8  mov     ebx, eax
0x180012dfa  cmp     eax, r13d
0x180012dfd  jnz     short loc_180012DA3
0x180012dff  jmp     loc_180012F53
0x180012e04  lea     rdx, aLockscope; "lockscope"
0x180012e0b  mov     rcx, rbx; String1
0x180012e0e  call    wcscmp_0
0x180012e13  test    eax, eax
0x180012e15  jnz     loc_180012EB8
0x180012e1b  lea     r9, [rsp+140h+var_110]; unsigned __int16 **
0x180012e20  mov     rcx, rsi; struct IXmlReader *
0x180012e23  lea     r8, [rsp+140h+String1]; unsigned __int16 **
0x180012e28  lea     rdx, [rsp+140h+var_108]; unsigned int *
0x180012e2d  call    ?XmlFindFirstSubElement@@YAJPEAUIXmlReader@@PEAIPEAPEBG2@Z; XmlFindFirstSubElement(IXmlReader *,uint *,ushort const * *,ushort const * *)
0x180012e32  jmp     short loc_180012EAC
0x180012e34  test    ebx, ebx
0x180012e36  js      loc_180012FBA
0x180012e3c  mov     rcx, [rsp+140h+String1]; String1
0x180012e41  lea     rdx, aDav; "DAV:"
0x180012e48  call    wcscmp_0
0x180012e4d  test    eax, eax
0x180012e4f  jnz     short loc_180012E96
0x180012e51  mov     rcx, [rsp+140h+var_110]; String1
0x180012e56  lea     rdx, aExclusive; "exclusive"
0x180012e5d  call    wcscmp_0
0x180012e62  test    eax, eax
0x180012e64  jnz     short loc_180012E73
0x180012e66  cmp     dword ptr [rdi+3Ch], 0FFFFFFFFh
0x180012e6a  jnz     loc_180013016
0x180012e70  mov     [rdi+3Ch], eax
0x180012e73  mov     rcx, [rsp+140h+var_110]; String1
0x180012e78  lea     rdx, aShared; "shared"
0x180012e7f  call    wcscmp_0
0x180012e84  test    eax, eax
0x180012e86  jnz     short loc_180012E96
0x180012e88  cmp     dword ptr [rdi+3Ch], 0FFFFFFFFh
0x180012e8c  jnz     loc_180013036
0x180012e92  mov     [rdi+3Ch], r13d
0x180012e96  mov     edx, [rsp+140h+var_108]; unsigned int
0x180012e9a  lea     r9, [rsp+140h+var_110]; unsigned __int16 **
0x180012e9f  lea     r8, [rsp+140h+String1]; unsigned __int16 **
0x180012ea4  mov     rcx, rsi; struct IXmlReader *
0x180012ea7  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x180012eac  mov     ebx, eax
0x180012eae  cmp     eax, r13d
0x180012eb1  jnz     short loc_180012E34
0x180012eb3  jmp     loc_180012F53
0x180012eb8  lea     rdx, aOwner; "owner"
0x180012ebf  mov     rcx, rbx; String1
0x180012ec2  call    wcscmp_0
0x180012ec7  test    eax, eax
0x180012ec9  jnz     loc_180012F53
0x180012ecf  test    r15d, r15d
0x180012ed2  jnz     loc_180013056
0x180012ed8  lea     r8, [rsp+140h+var_F8]; int *
0x180012edd  mov     rcx, rsi; struct IXmlReader *
0x180012ee0  lea     rdx, [rsp+140h+var_E8]; struct STRU *
0x180012ee5  call    ?XmlFindLanguageTag@@YAJPEAUIXmlReader@@PEAVSTRU@@PEAH@Z; XmlFindLanguageTag(IXmlReader *,STRU *,int *)
0x180012eea  mov     ebx, eax
0x180012eec  test    eax, eax
0x180012eee  js      loc_180012FBA
0x180012ef4  lea     rcx, [rbp+40h+var_78]
0x180012ef8  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180012efe  cmp     [rsp+140h+var_F8], r15d
0x180012f03  jz      short loc_180012F0C
0x180012f05  mov     r8, [rsp+140h+var_C8]
0x180012f0a  jmp     short loc_180012F19
0x180012f0c  mov     eax, [rsp+140h+var_F4]
0x180012f10  neg     eax
0x180012f12  sbb     r8, r8
0x180012f15  and     r8, [rbp+40h+var_90]; unsigned __int16 *
0x180012f19  lea     rdx, [rbp+40h+var_78]; struct STRU *
0x180012f1d  mov     rcx, rsi; struct IXmlReader *
0x180012f20  call    ?ParseOwnerElement@@YAJPEAUIXmlReader@@PEAVSTRU@@PEBG@Z; ParseOwnerElement(IXmlReader *,STRU *,ushort const *)
0x180012f25  mov     ebx, eax
0x180012f27  test    eax, eax
0x180012f29  js      short loc_180012F42
0x180012f2b  mov     rdx, [rbp+40h+var_58]
0x180012f2f  mov     rcx, rdi
0x180012f32  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012f38  mov     ebx, eax
0x180012f3a  test    eax, eax
0x180012f3c  js      short loc_180012F42
0x180012f3e  mov     [rdi+40h], r13d
0x180012f42  lea     rcx, [rbp+40h+var_78]
0x180012f46  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012f4c  test    ebx, ebx
0x180012f4e  js      short loc_180012FBA
0x180012f50  mov     r15d, r13d
0x180012f53  mov     edx, [rsp+140h+var_F0]; unsigned int
0x180012f57  lea     r9, [rsp+140h+var_110]; unsigned __int16 **
0x180012f5c  lea     r8, [rsp+140h+String1]; unsigned __int16 **
0x180012f61  mov     rcx, rsi; struct IXmlReader *
0x180012f64  call    ?XmlFindNextSubElement@@YAJPEAUIXmlReader@@IPEAPEBG1@Z; XmlFindNextSubElement(IXmlReader *,uint,ushort const * *,ushort const * *)
0x180012f69  mov     ebx, eax
0x180012f6b  cmp     eax, r13d
0x180012f6e  jnz     loc_180012D51
0x180012f74  cmp     dword ptr [rdi+38h], 0FFFFFFFFh
0x180012f78  jz      short loc_180012F82
0x180012f7a  xor     ebx, ebx
0x180012f7c  cmp     dword ptr [rdi+3Ch], 0FFFFFFFFh
0x180012f80  jnz     short loc_180012FBA
0x180012f82  mov     rax, [r14]
0x180012f85  mov     rcx, r14
0x180012f88  mov     ebx, 80070057h
0x180012f8d  mov     rax, [rax+110h]
0x180012f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f99  xor     r8d, r8d
0x180012f9c  lea     rdx, aLockRequiredXm; "LOCK: Required XML Elements Missing"
0x180012fa3  mov     rcx, rax
0x180012fa6  mov     [rsp+140h+var_120], 3
0x180012fab  mov     rax, [rax]
0x180012fae  xor     r9d, r9d
0x180012fb1  mov     rax, [rax+20h]
0x180012fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fba  lea     rcx, [rsp+140h+var_E8]
0x180012fbf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012fc5  lea     rcx, [rbp+40h+var_B0]
0x180012fc9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180012fcf  mov     eax, ebx
0x180012fd1  mov     rcx, [rbp+40h+var_40]
0x180012fd5  xor     rcx, rsp; StackCookie
0x180012fd8  call    __security_check_cookie
0x180012fdd  add     rsp, 110h
0x180012fe4  pop     r15
0x180012fe6  pop     r14
0x180012fe8  pop     r13
0x180012fea  pop     rdi
0x180012feb  pop     rsi
0x180012fec  pop     rbx
0x180012fed  pop     rbp
0x180012fee  retn
0x180012fef  mov     rax, [r14]
0x180012ff2  mov     rcx, r14
0x180012ff5  mov     ebx, 80070057h
0x180012ffa  mov     rax, [rax+110h]
0x180013001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013006  lea     r8, aWrite; "write"
0x18001300d  lea     rdx, aUnexpectedXmlE; "Unexpected XML Element"
0x180013014  jmp     short loc_180012FA3
0x180013016  mov     rax, [r14]
0x180013019  mov     rcx, r14
0x18001301c  mov     ebx, 80070057h
0x180013021  mov     rax, [rax+110h]
0x180013028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302d  lea     r8, aExclusive; "exclusive"
0x180013034  jmp     short loc_18001300D
0x180013036  mov     rax, [r14]
0x180013039  mov     rcx, r14
0x18001303c  mov     ebx, 80070057h
0x180013041  mov     rax, [rax+110h]
0x180013048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001304d  lea     r8, aShared; "shared"
0x180013054  jmp     short loc_18001300D
0x180013056  mov     rax, [r14]
0x180013059  mov     rcx, r14
0x18001305c  mov     ebx, 80070057h
0x180013061  mov     rax, [rax+110h]
0x180013068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001306d  lea     r8, aOwner; "owner"
0x180013074  jmp     short loc_18001300D
```
