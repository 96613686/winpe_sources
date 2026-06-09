# CWcnPageProfileCreateNew::UpdateSecurityDisplayInformation(void)

- ea: `0x180016008`
- end: `0x1800162e8`
- name: `?UpdateSecurityDisplayInformation@CWcnPageProfileCreateNew@@AEAAXXZ`
- size: `736`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000bbc0`
- `0x180015498`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e19c`
- `0x18000e1dc`
- `0x1800143ac`
- `0x1800156c0`
- `0x180016008`
- `0x18001f154`
- `0x18001f6b8`
- `0x18002de1c`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x180016249`
- `USER32!SetDlgItemTextW` at `0x180016263`
- `USER32!SetDlgItemTextW` at `0x180016249`
- `USER32!SetDlgItemTextW` at `0x180016263`
- `USER32!SendMessageW` at `0x180016140`
- `USER32!SendMessageW` at `0x180016166`
- `USER32!SendMessageW` at `0x18001627f`
- `USER32!SendMessageW` at `0x180016140`
- `USER32!SendMessageW` at `0x180016166`
- `USER32!SendMessageW` at `0x18001627f`
- `USER32!GetDlgItem` at `0x180016102`
- `USER32!GetDlgItem` at `0x18001612c`
- `USER32!GetDlgItem` at `0x180016152`
- `USER32!GetDlgItem` at `0x180016102`
- `USER32!GetDlgItem` at `0x18001612c`
- `USER32!GetDlgItem` at `0x180016152`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::UpdateSecurityDisplayInformation(HWND *this)
{
  CWcnPageProfileCreateNew *v2; // rcx
  int v3; // ebp
  UINT v4; // esi
  int v5; // r14d
  const char *Indent; // rax
  __int64 v7; // r10
  unsigned int i; // ecx
  UINT v9; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  WPARAM v12; // rbp
  int v13; // ecx
  HWND DlgItem; // rax
  WPARAM v15; // r8
  HWND v16; // rax
  int v17; // eax
  int v18; // ebx
  _QWORD *v19; // r10
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // r10
  WCHAR Buffer[128]; // [rsp+30h] [rbp-558h] BYREF
  WCHAR String[256]; // [rsp+130h] [rbp-458h] BYREF
  WCHAR v25[256]; // [rsp+330h] [rbp-258h] BYREF

  v2 = (CWcnPageProfileCreateNew *)(28LL
                                  * CWcnPageProfileCreateNew::GetSelectedItemHelper(
                                      (CWcnPageProfileCreateNew *)this,
                                      this[41]));
  v3 = *(_DWORD *)&byte_1800369E0[(_QWORD)v2];
  v4 = 0;
  v5 = *(_DWORD *)&byte_1800369E0[28 * CWcnPageProfileCreateNew::GetSelectedItemHelper(v2, this[43]) + 4];
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v7 + 16), 53, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  for ( i = 0; ; ++i )
  {
    v9 = 4372;
    if ( i >= 3 )
      goto LABEL_15;
    v10 = 28LL * i;
    if ( *(_DWORD *)&byte_1800369E0[v10] == v3 && *(_DWORD *)&byte_1800369E0[v10 + 4] == v5 )
      break;
  }
  v11 = *(_DWORD *)&byte_1800369E0[v10 + 12];
  v12 = 0;
  *((_DWORD *)this + 157) = *(_DWORD *)&byte_1800369E0[v10 + 24];
  v4 = *(_DWORD *)&byte_1800369E0[v10 + 16];
  if ( !v11 )
  {
LABEL_15:
    v12 = (WPARAM)this[81];
    DlgItem = GetDlgItem(this[21], 2304);
    v15 = 0;
    goto LABEL_16;
  }
  v13 = v11 - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
      goto LABEL_17;
    v12 = (WPARAM)this[79];
  }
  else
  {
    v12 = (WPARAM)this[80];
  }
  v9 = 4371;
  DlgItem = GetDlgItem(this[21], 2304);
  v15 = 1;
LABEL_16:
  SendMessageW(DlgItem, 0xF1u, v15, 0);
LABEL_17:
  v16 = GetDlgItem(this[21], 2951);
  SendMessageW(v16, 0x170u, v12, 0);
  v17 = WcnUxLoadString(v9, 0x100u, String);
  v18 = v17;
  if ( v17 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v20 = 54;
    goto LABEL_21;
  }
  v17 = WcnUxLoadString(v4, 0x80u, Buffer);
  v18 = v17;
  if ( v17 < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_32;
    v20 = 55;
    goto LABEL_21;
  }
  v17 = WcnUxFormatString(0x1115u, 0x100u, v25, Buffer);
  v18 = v17;
  if ( v17 >= 0 )
  {
    SetDlgItemTextW(this[21], 2952, String);
    SetDlgItemTextW(this[21], 2953, v25);
    SendMessageW(this[39], 0xC5u, *((unsigned int *)this + 157), 0);
    CWcnPageProfileCreateNew::RecalculateVisibleControls((CWcnPageProfileCreateNew *)this);
    goto LABEL_31;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v20 = 56;
LABEL_21:
    WPP_SF_d(v19[2], v20, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, (unsigned int)v17);
LABEL_31:
    v19 = WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( v19 != &WPP_GLOBAL_Control && (v18 < 0 || *((_BYTE *)v19 + 25) >= 6u) )
  {
    v21 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v22 + 16), 57, (unsigned int)WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, v21, v18);
  }
}

```

## disassembly

```asm
0x180016008  push    rbx
0x18001600a  push    rbp
0x18001600b  push    rsi
0x18001600c  push    rdi
0x18001600d  push    r12
0x18001600f  push    r13
0x180016011  push    r14
0x180016013  push    r15
0x180016015  sub     rsp, 548h
0x18001601c  mov     rax, cs:__security_cookie
0x180016023  xor     rax, rsp
0x180016026  mov     [rsp+588h+var_58], rax
0x18001602e  mov     rdx, [rcx+148h]; HWND
0x180016035  mov     rdi, rcx
0x180016038  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x18001603d  mov     rdx, [rdi+158h]; HWND
0x180016044  lea     r12, byte_1800369E0
0x18001604b  mov     eax, eax
0x18001604d  imul    rcx, rax, 1Ch; this
0x180016051  mov     ebp, [rcx+r12]
0x180016055  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x18001605a  mov     eax, eax
0x18001605c  imul    rcx, rax, 1Ch
0x180016060  xor     esi, esi
0x180016062  mov     r14d, [rcx+r12+4]
0x180016067  mov     r10, cs:WPP_GLOBAL_Control
0x18001606e  lea     r15, WPP_GLOBAL_Control
0x180016075  lea     r13, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x18001607c  cmp     r10, r15
0x18001607f  jz      short loc_1800160A2
0x180016081  cmp     byte ptr [r10+19h], 6
0x180016086  jb      short loc_1800160A2
0x180016088  lea     ecx, [rsi+1]; int
0x18001608b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180016090  mov     rcx, [r10+10h]
0x180016094  lea     edx, [rsi+35h]
0x180016097  mov     r9, rax
0x18001609a  mov     r8, r13
0x18001609d  call    WPP_SF_s
0x1800160a2  xor     ecx, ecx
0x1800160a4  mov     ebx, 1114h
0x1800160a9  cmp     ecx, 3
0x1800160ac  jnb     short loc_180016119
0x1800160ae  mov     eax, ecx
0x1800160b0  imul    rdx, rax, 1Ch
0x1800160b4  cmp     [rdx+r12], ebp
0x1800160b8  jnz     short loc_1800160C1
0x1800160ba  cmp     [rdx+r12+4], r14d
0x1800160bf  jz      short loc_1800160C5
0x1800160c1  inc     ecx
0x1800160c3  jmp     short loc_1800160A4
0x1800160c5  mov     ecx, [rdx+r12+0Ch]
0x1800160ca  xor     ebp, ebp
0x1800160cc  mov     eax, [rdx+r12+18h]
0x1800160d1  mov     [rdi+274h], eax
0x1800160d7  mov     esi, [rdx+r12+10h]
0x1800160dc  test    ecx, ecx
0x1800160de  jz      short loc_180016119
0x1800160e0  sub     ecx, 1
0x1800160e3  jz      short loc_180016110
0x1800160e5  cmp     ecx, 1
0x1800160e8  jnz     short loc_180016146
0x1800160ea  mov     rbp, [rdi+278h]
0x1800160f1  mov     rcx, [rdi+0A8h]; hDlg
0x1800160f8  mov     edx, 900h; nIDDlgItem
0x1800160fd  mov     ebx, 1113h
0x180016102  call    cs:__imp_GetDlgItem
0x180016108  mov     r8d, 1
0x18001610e  jmp     short loc_180016135
0x180016110  mov     rbp, [rdi+280h]
0x180016117  jmp     short loc_1800160F1
0x180016119  mov     rcx, [rdi+0A8h]; hDlg
0x180016120  mov     edx, 900h; nIDDlgItem
0x180016125  mov     rbp, [rdi+288h]
0x18001612c  call    cs:__imp_GetDlgItem
0x180016132  xor     r8d, r8d; wParam
0x180016135  xor     r9d, r9d; lParam
0x180016138  mov     edx, 0F1h; Msg
0x18001613d  mov     rcx, rax; hWnd
0x180016140  call    cs:__imp_SendMessageW
0x180016146  mov     rcx, [rdi+0A8h]; hDlg
0x18001614d  mov     edx, 0B87h; nIDDlgItem
0x180016152  call    cs:__imp_GetDlgItem
0x180016158  xor     r9d, r9d; lParam
0x18001615b  mov     r8, rbp; wParam
0x18001615e  mov     rcx, rax; hWnd
0x180016161  mov     edx, 170h; Msg
0x180016166  call    cs:__imp_SendMessageW
0x18001616c  mov     ebp, 100h
0x180016171  lea     r8, [rsp+588h+String]; lpBuffer
0x180016179  mov     edx, ebp; cchBufferMax
0x18001617b  mov     ecx, ebx; uID
0x18001617d  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x180016182  mov     ebx, eax
0x180016184  test    eax, eax
0x180016186  jns     short loc_1800161BC
0x180016188  mov     r10, cs:WPP_GLOBAL_Control
0x18001618f  cmp     r10, r15
0x180016192  jz      loc_1800162C4
0x180016198  cmp     byte ptr [r10+19h], 2
0x18001619d  jb      loc_180016294
0x1800161a3  mov     edx, 36h ; '6'
0x1800161a8  mov     rcx, [r10+10h]
0x1800161ac  mov     r9d, eax
0x1800161af  mov     r8, r13
0x1800161b2  call    WPP_SF_d
0x1800161b7  jmp     loc_18001628D
0x1800161bc  lea     r8, [rsp+588h+Buffer]; lpBuffer
0x1800161c1  mov     edx, 80h; cchBufferMax
0x1800161c6  mov     ecx, esi; uID
0x1800161c8  call    ?WcnUxLoadString@@YAJIKPEAG@Z; WcnUxLoadString(uint,ulong,ushort *)
0x1800161cd  mov     ebx, eax
0x1800161cf  test    eax, eax
0x1800161d1  jns     short loc_1800161F5
0x1800161d3  mov     r10, cs:WPP_GLOBAL_Control
0x1800161da  cmp     r10, r15
0x1800161dd  jz      loc_1800162C4
0x1800161e3  cmp     byte ptr [r10+19h], 2
0x1800161e8  jb      loc_180016294
0x1800161ee  mov     edx, 37h ; '7'
0x1800161f3  jmp     short loc_1800161A8
0x1800161f5  lea     r9, [rsp+588h+Buffer]
0x1800161fa  mov     edx, ebp; nSize
0x1800161fc  lea     r8, [rsp+588h+var_258]; unsigned __int16 *
0x180016204  mov     ecx, 1115h; dwMessageId
0x180016209  call    ?WcnUxFormatString@@YAJIKPEAGZZ; WcnUxFormatString(uint,ulong,ushort *,...)
0x18001620e  mov     ebx, eax
0x180016210  test    eax, eax
0x180016212  jns     short loc_180016235
0x180016214  mov     r10, cs:WPP_GLOBAL_Control
0x18001621b  cmp     r10, r15
0x18001621e  jz      loc_1800162C4
0x180016224  cmp     byte ptr [r10+19h], 2
0x180016229  jb      short loc_180016294
0x18001622b  mov     edx, 38h ; '8'
0x180016230  jmp     loc_1800161A8
0x180016235  mov     rcx, [rdi+0A8h]; hDlg
0x18001623c  lea     r8, [rsp+588h+String]; lpString
0x180016244  mov     edx, 0B88h; nIDDlgItem
0x180016249  call    cs:__imp_SetDlgItemTextW
0x18001624f  mov     rcx, [rdi+0A8h]; hDlg
0x180016256  lea     r8, [rsp+588h+var_258]; lpString
0x18001625e  mov     edx, 0B89h; nIDDlgItem
0x180016263  call    cs:__imp_SetDlgItemTextW
0x180016269  mov     r8d, [rdi+274h]; wParam
0x180016270  xor     r9d, r9d; lParam
0x180016273  mov     rcx, [rdi+138h]; hWnd
0x18001627a  mov     edx, 0C5h; Msg
0x18001627f  call    cs:__imp_SendMessageW
0x180016285  mov     rcx, rdi; this
0x180016288  call    ?RecalculateVisibleControls@CWcnPageProfileCreateNew@@AEAAXXZ; CWcnPageProfileCreateNew::RecalculateVisibleControls(void)
0x18001628d  mov     r10, cs:WPP_GLOBAL_Control
0x180016294  cmp     r10, r15
0x180016297  jz      short loc_1800162C4
0x180016299  test    ebx, ebx
0x18001629b  js      short loc_1800162A4
0x18001629d  cmp     byte ptr [r10+19h], 6
0x1800162a2  jb      short loc_1800162C4
0x1800162a4  or      ecx, 0FFFFFFFFh; int
0x1800162a7  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800162ac  mov     rcx, [r10+10h]
0x1800162b0  mov     edx, 39h ; '9'
0x1800162b5  mov     r9, rax
0x1800162b8  mov     [rsp+588h+var_568], ebx
0x1800162bc  mov     r8, r13
0x1800162bf  call    WPP_SF_sd
0x1800162c4  mov     rcx, [rsp+588h+var_58]
0x1800162cc  xor     rcx, rsp; StackCookie
0x1800162cf  call    __security_check_cookie
0x1800162d4  add     rsp, 548h
0x1800162db  pop     r15
0x1800162dd  pop     r14
0x1800162df  pop     r13
0x1800162e1  pop     r12
0x1800162e3  pop     rdi
0x1800162e4  pop     rsi
0x1800162e5  pop     rbp
0x1800162e6  pop     rbx
0x1800162e7  retn
```
