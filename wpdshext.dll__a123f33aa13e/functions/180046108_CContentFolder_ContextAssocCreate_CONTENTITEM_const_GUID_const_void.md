# CContentFolder::_ContextAssocCreate(CONTENTITEM const *,_GUID const &,void * *)

- ea: `0x180046108`
- end: `0x180046634`
- name: `?_ContextAssocCreate@CContentFolder@@AEAAJPEFBUCONTENTITEM@@AEBU_GUID@@PEAPEAX@Z`
- size: `1324`
- prototype: `int(CContentFolder *__hidden this, const struct CONTENTITEM *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001da0`

## callees

- `0x180004110`
- `0x180004190`
- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x18003912c`
- `0x180039e80`
- `0x180046108`
- `0x18007559c`
- `0x180078010`

## import_xrefs

- `SHLWAPI!AssocCreate` at `0x1800461b0`
- `SHLWAPI!AssocCreate` at `0x1800461b0`
- `SHLWAPI!PathFindExtensionW` at `0x18004649e`
- `SHLWAPI!PathFindExtensionW` at `0x18004649e`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800464c8`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800464c8`

## string_xrefs

- `0x1800463a3`: `WPDContextMenu.Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentFolder::_ContextAssocCreate(
        CContentFolder *this,
        const struct CONTENTITEM *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  HRESULT v7; // eax
  PVOID *v8; // rcx
  __int64 v9; // rdx
  const unsigned __int16 *v10; // r8
  CContentFolder *v11; // rcx
  unsigned int v12; // r9d
  const WCHAR *v13; // rax
  const WCHAR *ExtensionW; // rsi
  unsigned int i; // ebx
  unsigned int v16; // eax
  CLSID clsid; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv[2]; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[64]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v21[8]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v22[6]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v23[264]; // [rsp+140h] [rbp+40h] BYREF

  ppv[0] = 0;
  *(_OWORD *)v21 = *(_OWORD *)L"WPDContextMenu.Generic";
  v22[0] = *(_OWORD *)L"xtMenu.Generic";
  *(_OWORD *)((char *)v22 + 14) = *(_OWORD *)L"Generic";
  memset((char *)&v22[1] + 14, 0, 32);
  memset((char *)&v22[3] + 14, 0, 22);
  if ( !a4 )
  {
    v6 = -2147467261;
LABEL_56:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  *a4 = 0;
  clsid = CLSID_QueryAssociations;
  v7 = AssocCreate(&clsid, &IID_IQueryAssociations, ppv);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_57;
    v9 = 184;
LABEL_7:
    WPP_SF_d(v8[2], v9, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v7);
    goto LABEL_56;
  }
  if ( (*((_BYTE *)a2 + 10) & 2) != 0 )
  {
    v10 = L"WPDContextMenu.Folder";
  }
  else
  {
    clsid = *(CLSID *)((char *)a2 + 42);
    if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_IMAGE, 0x10u) )
    {
      v10 = L"WPDContextMenu.Image";
    }
    else
    {
      clsid = *(CLSID *)((char *)a2 + 42);
      if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_AUDIO, 0x10u) )
      {
        v10 = L"WPDContextMenu.Audio";
      }
      else
      {
        clsid = *(CLSID *)((char *)a2 + 42);
        if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_VIDEO, 0x10u) )
        {
          v10 = L"WPDContextMenu.Video";
        }
        else
        {
          clsid = *(CLSID *)((char *)a2 + 42);
          if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_PLAYLIST, 0x10u) )
          {
            v10 = L"WPDContextMenu.Playlist";
          }
          else
          {
            clsid = *(CLSID *)((char *)a2 + 42);
            if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_DOCUMENT, 0x10u) )
            {
              v10 = L"WPDContextMenu.Document";
            }
            else
            {
              clsid = *(CLSID *)((char *)a2 + 42);
              if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_CONTACT, 0x10u) )
              {
                v10 = L"WPDContextMenu.Contact";
              }
              else
              {
                clsid = *(CLSID *)((char *)a2 + 42);
                if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_EMAIL, 0x10u) )
                {
                  v10 = L"WPDContextMenu.Email";
                }
                else
                {
                  clsid = *(CLSID *)((char *)a2 + 42);
                  if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_APPOINTMENT, 0x10u) )
                  {
                    v10 = L"WPDContextMenu.Appointment";
                  }
                  else
                  {
                    clsid = *(CLSID *)((char *)a2 + 42);
                    if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_TASK, 0x10u) )
                    {
                      v10 = L"WPDContextMenu.Task";
                    }
                    else
                    {
                      clsid = *(CLSID *)((char *)a2 + 42);
                      if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_MEMO, 0x10u) )
                      {
                        v10 = L"WPDContextMenu.Memo";
                      }
                      else
                      {
                        clsid = *(CLSID *)((char *)a2 + 42);
                        if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_IMAGE_ALBUM, 0x10u) )
                        {
                          v10 = L"WPDContextMenu.ImageAlbum";
                        }
                        else
                        {
                          clsid = *(CLSID *)((char *)a2 + 42);
                          if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_AUDIO_ALBUM, 0x10u) )
                          {
                            v10 = L"WPDContextMenu.AudioAlbum";
                          }
                          else
                          {
                            clsid = *(CLSID *)((char *)a2 + 42);
                            if ( !memcmp_0(&clsid, &WPD_CONTENT_TYPE_VIDEO_ALBUM, 0x10u) )
                            {
                              v10 = L"WPDContextMenu.VideoAlbum";
                            }
                            else
                            {
                              clsid = *(CLSID *)((char *)a2 + 42);
                              if ( memcmp_0(&clsid, &WPD_CONTENT_TYPE_MIXED_CONTENT_ALBUM, 0x10u) )
                              {
                                v13 = CContentFolder::_Name(v11, a2, v23, v12);
                                ExtensionW = PathFindExtensionW(v13);
                                if ( ExtensionW )
                                {
                                  for ( i = 0; i < 0x23; ++i )
                                  {
                                    if ( !StrCmpICW(ExtensionW, off_18007BB40[2 * (int)i]) )
                                    {
                                      v10 = off_18007BB40[2 * (int)i + 1];
                                      goto LABEL_44;
                                    }
                                  }
                                }
                                goto LABEL_48;
                              }
                              v10 = L"WPDContextMenu.MixedAlbum";
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_44:
  v7 = StringCchCopyW(v21, 0x32u, v10);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_57;
    v9 = 185;
    goto LABEL_7;
  }
LABEL_48:
  v7 = (*(__int64 (__fastcall **)(void *, _QWORD, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppv[0] + 24LL))(
         ppv[0],
         0,
         v21,
         0,
         0);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_57;
    v9 = 186;
    goto LABEL_7;
  }
  v6 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv[0])(
         ppv[0],
         &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57,
         a4);
  if ( v6 >= 0 )
    goto LABEL_60;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_60;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v16 = (unsigned int)CGuidToString::CGuidToString(sz, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57);
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      187,
      (unsigned int)WPP_953c7f1870f230da5c3777fec273291e_Traceguids,
      v16,
      v6);
    goto LABEL_56;
  }
LABEL_57:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 )
    WPP_SF_d(v8[2], 188, WPP_953c7f1870f230da5c3777fec273291e_Traceguids, (unsigned int)v6);
LABEL_60:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180046108  mov     [rsp-8+arg_0], rbx
0x18004610d  push    rbp
0x18004610e  push    rsi
0x18004610f  push    rdi
0x180046110  push    r13
0x180046112  push    r14
0x180046114  lea     rbp, [rsp-260h]
0x18004611c  sub     rsp, 360h
0x180046123  mov     rax, cs:__security_cookie
0x18004612a  xor     rax, rsp
0x18004612d  mov     [rbp+280h+var_30], rax
0x180046134  mov     r14, r9
0x180046137  mov     rdi, rdx
0x18004613a  mov     [rsp+380h+ppv], 0
0x180046143  movups  xmm0, xmmword ptr cs:aWpdcontextmenu_0; "WPDContextMenu.Generic"
0x18004614a  movaps  xmmword ptr [rbp+280h+var_2B0], xmm0
0x18004614e  movups  xmm1, xmmword ptr cs:aWpdcontextmenu_0+10h; "xtMenu.Generic"
0x180046155  movaps  xmmword ptr [rbp+280h+var_2A0], xmm1
0x180046159  movups  xmm0, xmmword ptr cs:aWpdcontextmenu_0+1Eh; "Generic"
0x180046160  movups  xmmword ptr [rbp+280h+var_2A0+0Eh], xmm0
0x180046164  xorps   xmm1, xmm1
0x180046167  xor     eax, eax
0x180046169  movups  [rbp+280h+var_282], xmm1
0x18004616d  movups  [rbp+280h+var_272], xmm1
0x180046171  movups  xmmword ptr [rbp+280h+var_262], xmm1
0x180046175  mov     qword ptr [rbp+280h+var_262+0Eh], rax
0x180046179  test    r9, r9
0x18004617c  jnz     short loc_18004618F
0x18004617e  mov     ebx, 80004003h
0x180046183  lea     rdi, WPP_GLOBAL_Control
0x18004618a  jmp     loc_1800465D7
0x18004618f  mov     [r9], rax
0x180046192  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x180046199  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x18004619f  lea     r8, [rsp+380h+ppv]; ppv
0x1800461a4  lea     rdx, IID_IQueryAssociations; riid
0x1800461ab  lea     rcx, [rsp+380h+clsid]; clsid
0x1800461b0  call    cs:__imp_AssocCreate
0x1800461b6  mov     ebx, eax
0x1800461b8  test    eax, eax
0x1800461ba  jns     short loc_1800461FA
0x1800461bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800461c3  lea     rdi, WPP_GLOBAL_Control
0x1800461ca  cmp     rcx, rdi
0x1800461cd  jz      loc_180046602
0x1800461d3  test    byte ptr [rcx+1Ch], 2
0x1800461d7  jz      loc_1800465DE
0x1800461dd  mov     edx, 0B8h
0x1800461e2  mov     r9d, eax
0x1800461e5  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800461ec  mov     rcx, [rcx+10h]
0x1800461f0  call    WPP_SF_d
0x1800461f5  jmp     loc_1800465D7
0x1800461fa  test    byte ptr [rdi+0Ah], 2
0x1800461fe  jz      short loc_18004620C
0x180046200  lea     r8, aWpdcontextmenu_16; "WPDContextMenu.Folder"
0x180046207  jmp     loc_1800464DB
0x18004620c  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046210  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x180046216  mov     ebx, 10h
0x18004621b  mov     r8d, ebx; Size
0x18004621e  lea     rdx, WPD_CONTENT_TYPE_IMAGE; Buf2
0x180046225  lea     rcx, [rsp+380h+clsid]; Buf1
0x18004622a  call    memcmp_0
0x18004622f  test    eax, eax
0x180046231  jnz     short loc_18004623F
0x180046233  lea     r8, aWpdcontextmenu; "WPDContextMenu.Image"
0x18004623a  jmp     loc_1800464DB
0x18004623f  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046243  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x180046249  mov     r8, rbx; Size
0x18004624c  lea     rdx, WPD_CONTENT_TYPE_AUDIO; Buf2
0x180046253  lea     rcx, [rsp+380h+clsid]; Buf1
0x180046258  call    memcmp_0
0x18004625d  test    eax, eax
0x18004625f  jnz     short loc_18004626D
0x180046261  lea     r8, aWpdcontextmenu_11; "WPDContextMenu.Audio"
0x180046268  jmp     loc_1800464DB
0x18004626d  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046271  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x180046277  mov     r8, rbx; Size
0x18004627a  lea     rdx, WPD_CONTENT_TYPE_VIDEO; Buf2
0x180046281  lea     rcx, [rsp+380h+clsid]; Buf1
0x180046286  call    memcmp_0
0x18004628b  test    eax, eax
0x18004628d  jnz     short loc_18004629B
0x18004628f  lea     r8, aWpdcontextmenu_7; "WPDContextMenu.Video"
0x180046296  jmp     loc_1800464DB
0x18004629b  movups  xmm0, xmmword ptr [rdi+2Ah]
0x18004629f  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x1800462a5  mov     r8, rbx; Size
0x1800462a8  lea     rdx, WPD_CONTENT_TYPE_PLAYLIST; Buf2
0x1800462af  lea     rcx, [rsp+380h+clsid]; Buf1
0x1800462b4  call    memcmp_0
0x1800462b9  test    eax, eax
0x1800462bb  jnz     short loc_1800462C9
0x1800462bd  lea     r8, aWpdcontextmenu_15; "WPDContextMenu.Playlist"
0x1800462c4  jmp     loc_1800464DB
0x1800462c9  movups  xmm0, xmmword ptr [rdi+2Ah]
0x1800462cd  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x1800462d3  mov     r8, rbx; Size
0x1800462d6  lea     rdx, WPD_CONTENT_TYPE_DOCUMENT; Buf2
0x1800462dd  lea     rcx, [rsp+380h+clsid]; Buf1
0x1800462e2  call    memcmp_0
0x1800462e7  test    eax, eax
0x1800462e9  jnz     short loc_1800462F7
0x1800462eb  lea     r8, aWpdcontextmenu_8; "WPDContextMenu.Document"
0x1800462f2  jmp     loc_1800464DB
0x1800462f7  movups  xmm0, xmmword ptr [rdi+2Ah]
0x1800462fb  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x180046301  mov     r8, rbx; Size
0x180046304  lea     rdx, WPD_CONTENT_TYPE_CONTACT; Buf2
0x18004630b  lea     rcx, [rsp+380h+clsid]; Buf1
0x180046310  call    memcmp_0
0x180046315  test    eax, eax
0x180046317  jnz     short loc_180046325
0x180046319  lea     r8, aWpdcontextmenu_17; "WPDContextMenu.Contact"
0x180046320  jmp     loc_1800464DB
0x180046325  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046329  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x18004632f  mov     r8, rbx; Size
0x180046332  lea     rdx, WPD_CONTENT_TYPE_EMAIL; Buf2
0x180046339  lea     rcx, [rsp+380h+clsid]; Buf1
0x18004633e  call    memcmp_0
0x180046343  test    eax, eax
0x180046345  jnz     short loc_180046353
0x180046347  lea     r8, aWpdcontextmenu_3; "WPDContextMenu.Email"
0x18004634e  jmp     loc_1800464DB
0x180046353  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046357  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x18004635d  mov     r8, rbx; Size
0x180046360  lea     rdx, WPD_CONTENT_TYPE_APPOINTMENT; Buf2
0x180046367  lea     rcx, [rsp+380h+clsid]; Buf1
0x18004636c  call    memcmp_0
0x180046371  test    eax, eax
0x180046373  jnz     short loc_180046381
0x180046375  lea     r8, aWpdcontextmenu_2; "WPDContextMenu.Appointment"
0x18004637c  jmp     loc_1800464DB
0x180046381  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046385  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x18004638b  mov     r8, rbx; Size
0x18004638e  lea     rdx, WPD_CONTENT_TYPE_TASK; Buf2
0x180046395  lea     rcx, [rsp+380h+clsid]; Buf1
0x18004639a  call    memcmp_0
0x18004639f  test    eax, eax
0x1800463a1  jnz     short loc_1800463AF
0x1800463a3  lea     r8, aWpdcontextmenu_14; "WPDContextMenu.Task"
0x1800463aa  jmp     loc_1800464DB
0x1800463af  movups  xmm0, xmmword ptr [rdi+2Ah]
0x1800463b3  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x1800463b9  mov     r8, rbx; Size
0x1800463bc  lea     rdx, WPD_CONTENT_TYPE_MEMO; Buf2
0x1800463c3  lea     rcx, [rsp+380h+clsid]; Buf1
0x1800463c8  call    memcmp_0
0x1800463cd  test    eax, eax
0x1800463cf  jnz     short loc_1800463DD
0x1800463d1  lea     r8, aWpdcontextmenu_4; "WPDContextMenu.Memo"
0x1800463d8  jmp     loc_1800464DB
0x1800463dd  movups  xmm0, xmmword ptr [rdi+2Ah]
0x1800463e1  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x1800463e7  mov     r8, rbx; Size
0x1800463ea  lea     rdx, WPD_CONTENT_TYPE_IMAGE_ALBUM; Buf2
0x1800463f1  lea     rcx, [rsp+380h+clsid]; Buf1
0x1800463f6  call    memcmp_0
0x1800463fb  test    eax, eax
0x1800463fd  jnz     short loc_18004640B
0x1800463ff  lea     r8, aWpdcontextmenu_1; "WPDContextMenu.ImageAlbum"
0x180046406  jmp     loc_1800464DB
0x18004640b  movups  xmm0, xmmword ptr [rdi+2Ah]
0x18004640f  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x180046415  mov     r8, rbx; Size
0x180046418  lea     rdx, WPD_CONTENT_TYPE_AUDIO_ALBUM; Buf2
0x18004641f  lea     rcx, [rsp+380h+clsid]; Buf1
0x180046424  call    memcmp_0
0x180046429  test    eax, eax
0x18004642b  jnz     short loc_180046439
0x18004642d  lea     r8, aWpdcontextmenu_9; "WPDContextMenu.AudioAlbum"
0x180046434  jmp     loc_1800464DB
0x180046439  movups  xmm0, xmmword ptr [rdi+2Ah]
0x18004643d  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x180046443  mov     r8, rbx; Size
0x180046446  lea     rdx, WPD_CONTENT_TYPE_VIDEO_ALBUM; Buf2
0x18004644d  lea     rcx, [rsp+380h+clsid]; Buf1
0x180046452  call    memcmp_0
0x180046457  test    eax, eax
0x180046459  jnz     short loc_180046464
0x18004645b  lea     r8, aWpdcontextmenu_13; "WPDContextMenu.VideoAlbum"
0x180046462  jmp     short loc_1800464DB
0x180046464  movups  xmm0, xmmword ptr [rdi+2Ah]
0x180046468  movdqu  xmmword ptr [rsp+380h+clsid.Data1], xmm0
0x18004646e  mov     r8, rbx; Size
0x180046471  lea     rdx, WPD_CONTENT_TYPE_MIXED_CONTENT_ALBUM; Buf2
0x180046478  lea     rcx, [rsp+380h+clsid]; Buf1
0x18004647d  call    memcmp_0
0x180046482  test    eax, eax
0x180046484  jnz     short loc_18004648F
0x180046486  lea     r8, aWpdcontextmenu_5; "WPDContextMenu.MixedAlbum"
0x18004648d  jmp     short loc_1800464DB
0x18004648f  lea     r8, [rbp+280h+var_240]; unsigned __int16 *
0x180046493  mov     rdx, rdi; struct CONTENTITEM *
0x180046496  call    ?_Name@CContentFolder@@QEAAPEBGPEFBUCONTENTITEM@@PEAGI@Z; CContentFolder::_Name(CONTENTITEM const *,ushort *,uint)
0x18004649b  mov     rcx, rax; pszPath
0x18004649e  call    cs:__imp_PathFindExtensionW
0x1800464a4  mov     rsi, rax
0x1800464a7  test    rax, rax
0x1800464aa  jz      short loc_18004651A
0x1800464ac  xor     ebx, ebx
0x1800464ae  lea     r13, off_18007BB40; ".aiff"
0x1800464b5  cmp     ebx, 23h ; '#'
0x1800464b8  jnb     short loc_18004651A
0x1800464ba  movsxd  rdi, ebx
0x1800464bd  add     rdi, rdi
0x1800464c0  mov     rdx, [r13+rdi*8+0]; pszStr2
0x1800464c5  mov     rcx, rsi; pszStr1
0x1800464c8  call    cs:__imp_StrCmpICW
0x1800464ce  test    eax, eax
0x1800464d0  jz      short loc_1800464D6
0x1800464d2  inc     ebx
0x1800464d4  jmp     short loc_1800464B5
0x1800464d6  mov     r8, [r13+rdi*8+8]; unsigned __int16 *
0x1800464db  mov     edx, 32h ; '2'; unsigned __int64
0x1800464e0  lea     rcx, [rbp+280h+var_2B0]; unsigned __int16 *
0x1800464e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800464e9  mov     ebx, eax
0x1800464eb  test    eax, eax
0x1800464ed  jns     short loc_18004651A
0x1800464ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800464f6  lea     rdi, WPP_GLOBAL_Control
0x1800464fd  cmp     rcx, rdi
0x180046500  jz      loc_180046602
0x180046506  test    byte ptr [rcx+1Ch], 2
0x18004650a  jz      loc_1800465DE
0x180046510  mov     edx, 0B9h
0x180046515  jmp     loc_1800461E2
0x18004651a  mov     rcx, [rsp+380h+ppv]
0x18004651f  mov     rax, [rcx]
0x180046522  mov     [rsp+380h+var_360], 0
0x18004652b  xor     r9d, r9d
0x18004652e  lea     r8, [rbp+280h+var_2B0]
0x180046532  xor     edx, edx
0x180046534  mov     rax, [rax+18h]
0x180046538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004653d  mov     ebx, eax
0x18004653f  test    eax, eax
0x180046541  jns     short loc_18004656A
0x180046543  mov     rcx, cs:WPP_GLOBAL_Control
0x18004654a  lea     rdi, WPP_GLOBAL_Control
0x180046551  cmp     rcx, rdi
0x180046554  jz      loc_180046602
0x18004655a  test    byte ptr [rcx+1Ch], 2
0x18004655e  jz      short loc_1800465DE
0x180046560  mov     edx, 0BAh
0x180046565  jmp     loc_1800461E2
0x18004656a  mov     rcx, [rsp+380h+ppv]
0x18004656f  mov     rax, [rcx]
0x180046572  mov     r8, r14
0x180046575  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57
0x18004657c  mov     rax, [rax]
0x18004657f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046584  mov     ebx, eax
0x180046586  test    eax, eax
0x180046588  jns     short loc_180046602
0x18004658a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046591  lea     rdi, WPP_GLOBAL_Control
0x180046598  cmp     rcx, rdi
0x18004659b  jz      short loc_180046602
0x18004659d  test    byte ptr [rcx+1Ch], 2
0x1800465a1  jz      short loc_1800465DE
0x1800465a3  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; rguid
0x1800465aa  lea     rcx, [rsp+380h+sz]; lpsz
0x1800465af  call    ??0CGuidToString@@QEAA@AEBU_GUID@@@Z; CGuidToString::CGuidToString(_GUID const &)
0x1800465b4  mov     edx, 0BBh
0x1800465b9  mov     dword ptr [rsp+380h+var_360], ebx
0x1800465bd  mov     r9, rax
0x1800465c0  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800465c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800465ce  mov     rcx, [rcx+10h]
0x1800465d2  call    WPP_SF_Sd
0x1800465d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800465de  cmp     rcx, rdi
0x1800465e1  jz      short loc_180046602
0x1800465e3  test    byte ptr [rcx+1Ch], 2
0x1800465e7  jz      short loc_180046602
0x1800465e9  mov     edx, 0BCh
0x1800465ee  mov     r9d, ebx
0x1800465f1  lea     r8, WPP_953c7f1870f230da5c3777fec273291e_Traceguids
0x1800465f8  mov     rcx, [rcx+10h]
0x1800465fc  call    WPP_SF_d
0x180046601  nop
0x180046602  lea     rcx, [rsp+380h+ppv]
0x180046607  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004660c  mov     eax, ebx
0x18004660e  mov     rcx, [rbp+280h+var_30]
0x180046615  xor     rcx, rsp; StackCookie
0x180046618  call    __security_check_cookie
0x18004661d  mov     rbx, [rsp+380h+arg_0]
0x180046625  add     rsp, 360h
0x18004662c  pop     r14
0x18004662e  pop     r13
0x180046630  pop     rdi
  ... truncated ...
```
