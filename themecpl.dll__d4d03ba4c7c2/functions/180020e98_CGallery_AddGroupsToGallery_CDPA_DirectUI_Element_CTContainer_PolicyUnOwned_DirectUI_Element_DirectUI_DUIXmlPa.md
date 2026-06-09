# CGallery::_AddGroupsToGallery(CDPA<DirectUI::Element,CTContainer_PolicyUnOwned<DirectUI::Element>> *,DirectUI::DUIXmlParser *,bool)

- ea: `0x180020e98`
- end: `0x180021130`
- name: `?_AddGroupsToGallery@CGallery@@AEAAJPEAV?$CDPA@VElement@DirectUI@@V?$CTContainer_PolicyUnOwned@VElement@DirectUI@@@@@@PEAVDUIXmlParser@DirectUI@@_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(CGallery *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800214d8`

## callees

- `0x180002280`
- `0x180008110`
- `0x180020e98`
- `0x180021138`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800210f6`
- `USER32!GetSysColor` at `0x18002104b`
- `USER32!GetSysColor` at `0x18002104b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020f4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180021011`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020f4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180021011`
- `DUI70!StrToID` at `0x180020f3c`
- `DUI70!StrToID` at `0x180020fff`
- `DUI70!StrToID` at `0x180020f3c`
- `DUI70!StrToID` at `0x180020fff`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18002106e`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18002106e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800210c9`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800210c9`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002102d`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002102d`
- `DUI70!?SetForegroundColor@Element@DirectUI@@QEAAJK@Z` at `0x18002105c`
- `DUI70!?SetForegroundColor@Element@DirectUI@@QEAAJK@Z` at `0x18002105c`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180020fb8`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180020fb8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800210a4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800210a4`

## pseudocode

```c
__int64 __fastcall CGallery::_AddGroupsToGallery(
        CGallery *this,
        struct _DPA **a2,
        struct DirectUI::DUIXmlParser *a3,
        char a4)
{
  __int64 v5; // rcx
  struct _DPA **v6; // rdi
  int v7; // ebx
  void *v8; // r13
  void *v9; // r12
  unsigned int v10; // esi
  struct _DPA *v11; // rcx
  int v12; // edx
  DirectUI::Element *Ptr; // rdi
  unsigned __int16 v14; // ax
  struct DirectUI::Element *Descendent; // rbp
  void *v16; // r15
  _DWORD *Children; // rax
  int v18; // ecx
  unsigned __int16 v19; // ax
  DirectUI::Element *v20; // rax
  DirectUI::Element *v21; // rbp
  DWORD SysColor; // eax
  __int64 v24; // [rsp+20h] [rbp-178h]
  DirectUI::Value *v26; // [rsp+38h] [rbp-160h] BYREF
  struct DirectUI::DUIXmlParser *v27; // [rsp+40h] [rbp-158h]
  struct _DPA **v28; // [rsp+48h] [rbp-150h]
  unsigned __int16 v29[128]; // [rsp+50h] [rbp-148h] BYREF

  v28 = a2;
  v5 = *((_QWORD *)this + 1);
  v6 = a2;
  v7 = 0;
  v27 = a3;
  v8 = (void *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2);
  v9 = (void *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), 1);
  v10 = 0;
  do
  {
    v11 = *v6;
    if ( *v6 )
      v12 = *(_DWORD *)v11;
    else
      v12 = 0;
    if ( (int)v10 >= v12 )
      break;
    Ptr = (DirectUI::Element *)DPA_GetPtr(v11, (int)v10);
    if ( v8 )
    {
      if ( v9 )
      {
        v14 = StrToID(v8);
        Descendent = DirectUI::Element::FindDescendent(Ptr, v14);
        if ( Descendent )
        {
          if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
                 *((_QWORD *)this + 1),
                 v10)
            || (*((_BYTE *)Descendent + 149) & 2) != 0 )
          {
            v16 = (void *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 16LL))(
                            *((_QWORD *)this + 1),
                            v10);
            if ( v16 )
            {
              v26 = 0;
              Children = (_DWORD *)DirectUI::Element::GetChildren(Descendent, &v26);
              if ( Children )
                v18 = *Children & 0xFFFFFFF;
              else
                v18 = 0;
              LODWORD(v24) = v18;
              v7 = StringCchPrintfW(v29, 0x80u, L"%s (%d)", v16, v24);
              if ( v7 >= 0 )
              {
                v19 = StrToID(v9);
                v20 = DirectUI::Element::FindDescendent(Ptr, v19);
                v21 = v20;
                if ( v20 )
                {
                  v7 = DirectUI::Element::SetContentString(v20, v29);
                  if ( v7 >= 0 )
                  {
                    if ( *((_BYTE *)this + 40) )
                    {
                      SysColor = GetSysColor(17);
                      DirectUI::Element::SetForegroundColor(v21, SysColor);
                    }
                    v7 = DirectUI::Element::Add(*(DirectUI::Element **)this, Ptr);
                    if ( v7 >= 0 )
                    {
                      Ptr = 0;
                      if ( !v10 )
                        v7 = CGallery::_AddLinksToGallery(this, v27, a4);
                    }
                  }
                }
              }
              if ( v26 )
                DirectUI::Value::Release(v26);
              CoTaskMemFree(v16);
            }
          }
        }
      }
    }
    if ( Ptr )
      DirectUI::Element::Destroy(Ptr, 1);
    v6 = v28;
    ++v10;
  }
  while ( v7 >= 0 );
  CoTaskMemFree(v8);
  CoTaskMemFree(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180020e98  mov     [rsp+arg_18], rbx
0x180020e9d  push    rbp
0x180020e9e  push    rsi
0x180020e9f  push    rdi
0x180020ea0  push    r12
0x180020ea2  push    r13
0x180020ea4  push    r14
0x180020ea6  push    r15
0x180020ea8  sub     rsp, 160h
0x180020eaf  mov     rax, cs:__security_cookie
0x180020eb6  xor     rax, rsp
0x180020eb9  mov     [rsp+198h+var_48], rax
0x180020ec1  mov     r14, rcx
0x180020ec4  mov     [rsp+198h+var_150], rdx
0x180020ec9  mov     rcx, [rcx+8]
0x180020ecd  mov     rdi, rdx
0x180020ed0  xor     ebx, ebx
0x180020ed2  mov     [rsp+198h+var_168], r9b
0x180020ed7  mov     [rsp+198h+var_158], r8
0x180020edc  mov     rax, [rcx]
0x180020edf  lea     edx, [rbx+2]
0x180020ee2  mov     rax, [rax+8]
0x180020ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020eeb  mov     rcx, [r14+8]
0x180020eef  lea     edx, [rbx+1]
0x180020ef2  mov     r13, rax
0x180020ef5  mov     rax, [rcx]
0x180020ef8  mov     rax, [rax+8]
0x180020efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f01  mov     r12, rax
0x180020f04  xor     esi, esi
0x180020f06  mov     rcx, [rdi]; hdpa
0x180020f09  test    rcx, rcx
0x180020f0c  jz      short loc_180020F12
0x180020f0e  mov     edx, [rcx]
0x180020f10  jmp     short loc_180020F14
0x180020f12  xor     edx, edx
0x180020f14  cmp     esi, edx
0x180020f16  jge     loc_1800210E4
0x180020f1c  movsxd  rdx, esi; i
0x180020f1f  call    DPA_GetPtr
0x180020f24  mov     rdi, rax
0x180020f27  test    r13, r13
0x180020f2a  jz      loc_1800210BF
0x180020f30  test    r12, r12
0x180020f33  jz      loc_1800210BF
0x180020f39  mov     rcx, r13
0x180020f3c  call    cs:__imp_StrToID
0x180020f43  nop     dword ptr [rax+rax+00h]
0x180020f48  movzx   edx, ax
0x180020f4b  mov     rcx, rdi
0x180020f4e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180020f55  nop     dword ptr [rax+rax+00h]
0x180020f5a  mov     rbp, rax
0x180020f5d  test    rax, rax
0x180020f60  jz      loc_1800210BF
0x180020f66  mov     rcx, [r14+8]
0x180020f6a  mov     edx, esi
0x180020f6c  mov     rax, [rcx]
0x180020f6f  mov     rax, [rax+18h]
0x180020f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f78  test    al, al
0x180020f7a  jnz     short loc_180020F89
0x180020f7c  test    byte ptr [rbp+95h], 2
0x180020f83  jz      loc_1800210BF
0x180020f89  mov     rcx, [r14+8]
0x180020f8d  mov     edx, esi
0x180020f8f  mov     rax, [rcx]
0x180020f92  mov     rax, [rax+10h]
0x180020f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f9b  mov     r15, rax
0x180020f9e  test    rax, rax
0x180020fa1  jz      loc_1800210BF
0x180020fa7  lea     rdx, [rsp+198h+var_160]
0x180020fac  mov     [rsp+198h+var_160], 0
0x180020fb5  mov     rcx, rbp
0x180020fb8  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180020fbf  nop     dword ptr [rax+rax+00h]
0x180020fc4  test    rax, rax
0x180020fc7  jz      short loc_180020FD3
0x180020fc9  mov     ecx, [rax]
0x180020fcb  and     ecx, 0FFFFFFFh
0x180020fd1  jmp     short loc_180020FD5
0x180020fd3  xor     ecx, ecx
0x180020fd5  mov     [rsp+198h+var_178], ecx
0x180020fd9  lea     r8, aSD; "%s (%d)"
0x180020fe0  lea     rcx, [rsp+198h+var_148]; unsigned __int16 *
0x180020fe5  mov     r9, r15
0x180020fe8  mov     edx, 80h; unsigned __int64
0x180020fed  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020ff2  mov     ebx, eax
0x180020ff4  test    eax, eax
0x180020ff6  js      loc_18002109A
0x180020ffc  mov     rcx, r12
0x180020fff  call    cs:__imp_StrToID
0x180021006  nop     dword ptr [rax+rax+00h]
0x18002100b  movzx   edx, ax
0x18002100e  mov     rcx, rdi
0x180021011  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180021018  nop     dword ptr [rax+rax+00h]
0x18002101d  mov     rbp, rax
0x180021020  test    rax, rax
0x180021023  jz      short loc_18002109A
0x180021025  lea     rdx, [rsp+198h+var_148]
0x18002102a  mov     rcx, rax
0x18002102d  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180021034  nop     dword ptr [rax+rax+00h]
0x180021039  mov     ebx, eax
0x18002103b  test    eax, eax
0x18002103d  js      short loc_18002109A
0x18002103f  cmp     byte ptr [r14+28h], 0
0x180021044  jz      short loc_180021068
0x180021046  mov     ecx, 11h; nIndex
0x18002104b  call    cs:__imp_GetSysColor
0x180021052  nop     dword ptr [rax+rax+00h]
0x180021057  mov     edx, eax
0x180021059  mov     rcx, rbp
0x18002105c  call    cs:__imp_?SetForegroundColor@Element@DirectUI@@QEAAJK@Z; DirectUI::Element::SetForegroundColor(ulong)
0x180021063  nop     dword ptr [rax+rax+00h]
0x180021068  mov     rcx, [r14]
0x18002106b  mov     rdx, rdi
0x18002106e  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180021075  nop     dword ptr [rax+rax+00h]
0x18002107a  mov     ebx, eax
0x18002107c  test    eax, eax
0x18002107e  js      short loc_18002109A
0x180021080  xor     edi, edi
0x180021082  test    esi, esi
0x180021084  jnz     short loc_18002109A
0x180021086  mov     r8b, [rsp+198h+var_168]; bool
0x18002108b  mov     rcx, r14; this
0x18002108e  mov     rdx, [rsp+198h+var_158]; struct DirectUI::DUIXmlParser *
0x180021093  call    ?_AddLinksToGallery@CGallery@@AEAAJPEAVDUIXmlParser@DirectUI@@_N@Z; CGallery::_AddLinksToGallery(DirectUI::DUIXmlParser *,bool)
0x180021098  mov     ebx, eax
0x18002109a  mov     rcx, [rsp+198h+var_160]
0x18002109f  test    rcx, rcx
0x1800210a2  jz      short loc_1800210B0
0x1800210a4  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800210ab  nop     dword ptr [rax+rax+00h]
0x1800210b0  mov     rcx, r15; pv
0x1800210b3  call    cs:__imp_CoTaskMemFree
0x1800210ba  nop     dword ptr [rax+rax+00h]
0x1800210bf  test    rdi, rdi
0x1800210c2  jz      short loc_1800210D5
0x1800210c4  mov     dl, 1
0x1800210c6  mov     rcx, rdi
0x1800210c9  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800210d0  nop     dword ptr [rax+rax+00h]
0x1800210d5  mov     rdi, [rsp+198h+var_150]
0x1800210da  inc     esi
0x1800210dc  test    ebx, ebx
0x1800210de  jns     loc_180020F06
0x1800210e4  mov     rcx, r13; pv
0x1800210e7  call    cs:__imp_CoTaskMemFree
0x1800210ee  nop     dword ptr [rax+rax+00h]
0x1800210f3  mov     rcx, r12; pv
0x1800210f6  call    cs:__imp_CoTaskMemFree
0x1800210fd  nop     dword ptr [rax+rax+00h]
0x180021102  mov     eax, ebx
0x180021104  mov     rcx, [rsp+198h+var_48]
0x18002110c  xor     rcx, rsp; StackCookie
0x18002110f  call    __security_check_cookie
0x180021114  mov     rbx, [rsp+198h+arg_18]
0x18002111c  add     rsp, 160h
0x180021123  pop     r15
0x180021125  pop     r14
0x180021127  pop     r13
0x180021129  pop     r12
0x18002112b  pop     rdi
0x18002112c  pop     rsi
0x18002112d  pop     rbp
0x18002112e  retn
```
