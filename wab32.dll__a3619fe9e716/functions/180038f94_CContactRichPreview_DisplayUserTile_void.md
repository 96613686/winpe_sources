# CContactRichPreview::_DisplayUserTile(void)

- ea: `0x180038f94`
- end: `0x180039116`
- name: `?_DisplayUserTile@CContactRichPreview@@AEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CContactRichPreview *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18003ad04`

## callees

- `0x180001610`
- `0x18000161c`
- `0x180002818`
- `0x180038f94`
- `0x18006bcac`
- `0x18006bf6c`
- `0x18006c19c`
- `0x180093010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800390ec`
- `GDI32!DeleteObject` at `0x1800390ec`
- `USER32!SendMessageW` at `0x1800390dc`
- `USER32!SendMessageW` at `0x1800390dc`
- `USER32!IsWindow` at `0x180038ffa`
- `USER32!IsWindow` at `0x180038ffa`
- `USER32!GetSysColor` at `0x180038fe6`
- `USER32!GetSysColor` at `0x180038fe6`

## pseudocode

```c
__int64 __fastcall CContactRichPreview::_DisplayUserTile(CContactRichPreview *this)
{
  DWORD SysColor; // eax
  HWND v3; // rcx
  DWORD v4; // edi
  int v5; // ebx
  unsigned int *v6; // r8
  unsigned int v7; // r9d
  int HBITMAP; // eax
  void *v9; // rdi
  _QWORD v11[2]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h]
  __int64 v13; // [rsp+50h] [rbp-20h]
  void *Block[2]; // [rsp+58h] [rbp-18h]
  struct tagSIZE v15; // [rsp+90h] [rbp+20h] BYREF
  struct IContact *v16; // [rsp+98h] [rbp+28h] BYREF
  LPARAM lParam; // [rsp+A0h] [rbp+30h] BYREF

  lParam = 0;
  v11[1] = 0;
  v11[0] = &CUserTile::`vftable';
  v13 = 0;
  v16 = 0;
  v12 = 0;
  *(_OWORD *)Block = 0;
  SysColor = GetSysColor(5);
  v3 = (HWND)*((_QWORD *)this + 4);
  v4 = SysColor;
  v15 = 0;
  if ( IsWindow(v3) )
  {
    v5 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IContact **))this + 38))(
           *((_QWORD *)this + 38),
           &GUID_f941b671_bda7_4f77_884a_f46462f226a7,
           &v16);
    if ( v5 >= 0 )
    {
      v5 = CUserTile::InitFromContact((CUserTile *)v11, v16);
      if ( v5 >= 0 )
      {
        if ( Block[1] )
        {
          operator delete(Block[1]);
          Block[1] = 0;
        }
        v6 = (unsigned int *)operator new(4u);
        if ( v6 )
        {
          *v6 = BYTE2(v4) | v4 & 0xFF00 | ((v4 | 0xFFFFFF00) << 16);
          Block[1] = v6;
        }
        else
        {
          Block[1] = 0;
        }
        v15.cy = *((_DWORD *)this + 78);
        v15.cx = v15.cy;
        HBITMAP = CUserTile::GetHBITMAP((CUserTile *)v11, &v15, (int)v6, v7, (HBITMAP *)&lParam);
        v9 = (void *)lParam;
        v5 = HBITMAP;
        if ( HBITMAP >= 0 )
        {
          SendMessageW(*((HWND *)this + 4), 0xF7u, 0, lParam);
          v5 = 0;
        }
        if ( v9 )
          DeleteObject(v9);
      }
    }
  }
  else
  {
    v5 = 1;
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
  CUserTile::~CUserTile((CUserTile *)v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180038f94  mov     [rsp-18h+arg_18], rbx
0x180038f99  push    rbp
0x180038f9a  push    rsi
0x180038f9b  push    rdi
0x180038f9c  mov     rbp, rsp
0x180038f9f  sub     rsp, 70h
0x180038fa3  mov     rsi, rcx
0x180038fa6  mov     [rbp+lParam], 0
0x180038fae  lea     rax, ??_7CUserTile@@6B@; const CUserTile::`vftable'
0x180038fb5  mov     [rbp+var_38], 0
0x180038fbd  xorps   xmm0, xmm0
0x180038fc0  mov     [rbp+var_40], rax
0x180038fc4  xorps   xmm1, xmm1
0x180038fc7  mov     [rbp+var_20], 0
0x180038fcf  mov     ecx, 5; nIndex
0x180038fd4  mov     [rbp+arg_8], 0
0x180038fdc  movdqu  [rbp+var_30], xmm0
0x180038fe1  movdqu  xmmword ptr [rbp+Block], xmm1
0x180038fe6  call    cs:__imp_GetSysColor
0x180038fec  mov     rcx, [rsi+20h]; hWnd
0x180038ff0  mov     edi, eax
0x180038ff2  mov     qword ptr [rbp+arg_0.cx], 0
0x180038ffa  call    cs:__imp_IsWindow
0x180039000  test    eax, eax
0x180039002  jnz     short loc_18003900C
0x180039004  lea     ebx, [rax+1]
0x180039007  jmp     loc_1800390F2
0x18003900c  mov     rcx, [rsi+130h]
0x180039013  lea     r8, [rbp+arg_8]
0x180039017  lea     rdx, _GUID_f941b671_bda7_4f77_884a_f46462f226a7
0x18003901e  mov     rax, [rcx]
0x180039021  mov     rax, [rax]
0x180039024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039029  mov     ebx, eax
0x18003902b  test    eax, eax
0x18003902d  js      loc_1800390F2
0x180039033  mov     rdx, [rbp+arg_8]; struct IContact *
0x180039037  lea     rcx, [rbp+var_40]; this
0x18003903b  call    ?InitFromContact@CUserTile@@QEAAJPEAUIContact@@@Z; CUserTile::InitFromContact(IContact *)
0x180039040  mov     ebx, eax
0x180039042  test    eax, eax
0x180039044  js      loc_1800390F2
0x18003904a  mov     rcx, [rbp+Block+8]; Block
0x18003904e  test    rcx, rcx
0x180039051  jz      short loc_180039060
0x180039053  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039058  mov     [rbp+Block+8], 0
0x180039060  mov     ecx, 4; Size
0x180039065  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003906a  mov     r8, rax; int
0x18003906d  test    rax, rax
0x180039070  jz      short loc_180039099
0x180039072  mov     eax, 0FFFFFF00h
0x180039077  movzx   edx, dil
0x18003907b  or      edx, eax
0x18003907d  movzx   ecx, di
0x180039080  and     ecx, eax
0x180039082  shl     edx, 10h
0x180039085  shr     edi, 10h
0x180039088  or      edx, ecx
0x18003908a  movzx   eax, dil
0x18003908e  or      edx, eax
0x180039090  mov     [r8], edx
0x180039093  mov     [rbp+Block+8], r8
0x180039097  jmp     short loc_1800390A1
0x180039099  mov     [rbp+Block+8], 0
0x1800390a1  mov     eax, [rsi+138h]
0x1800390a7  lea     rdx, [rbp+arg_0]; struct tagSIZE *
0x1800390ab  mov     [rbp+arg_0.cy], eax
0x1800390ae  lea     rcx, [rbp+var_40]; this
0x1800390b2  mov     [rbp+arg_0.cx], eax
0x1800390b5  lea     rax, [rbp+lParam]
0x1800390b9  mov     [rsp+70h+var_50], rax; HBITMAP *
0x1800390be  call    ?GetHBITMAP@CUserTile@@QEAAJPEBUtagSIZE@@HKPEAPEAUHBITMAP__@@@Z; CUserTile::GetHBITMAP(tagSIZE const *,int,ulong,HBITMAP__ * *)
0x1800390c3  mov     rdi, [rbp+lParam]
0x1800390c7  mov     ebx, eax
0x1800390c9  test    eax, eax
0x1800390cb  js      short loc_1800390E4
0x1800390cd  mov     rcx, [rsi+20h]; hWnd
0x1800390d1  mov     r9, rdi; lParam
0x1800390d4  xor     r8d, r8d; wParam
0x1800390d7  mov     edx, 0F7h; Msg
0x1800390dc  call    cs:__imp_SendMessageW
0x1800390e2  xor     ebx, ebx
0x1800390e4  test    rdi, rdi
0x1800390e7  jz      short loc_1800390F2
0x1800390e9  mov     rcx, rdi; ho
0x1800390ec  call    cs:__imp_DeleteObject
0x1800390f2  lea     rcx, [rbp+arg_8]
0x1800390f6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800390fb  lea     rcx, [rbp+var_40]; this
0x1800390ff  call    ??1CUserTile@@UEAA@XZ; CUserTile::~CUserTile(void)
0x180039104  mov     eax, ebx
0x180039106  mov     rbx, [rsp+70h+arg_18]
0x18003910e  add     rsp, 70h
0x180039112  pop     rdi
0x180039113  pop     rsi
0x180039114  pop     rbp
0x180039115  retn
```
