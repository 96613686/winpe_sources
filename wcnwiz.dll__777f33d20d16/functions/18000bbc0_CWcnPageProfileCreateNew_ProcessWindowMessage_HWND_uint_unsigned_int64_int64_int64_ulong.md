# CWcnPageProfileCreateNew::ProcessWindowMessage(HWND__ *,uint,unsigned __int64,__int64,__int64 &,ulong)

- ea: `0x18000bbc0`
- end: `0x18000be22`
- name: `?ProcessWindowMessage@CWcnPageProfileCreateNew@@UEAAHPEAUHWND__@@I_K_JAEA_JK@Z`
- size: `610`
- prototype: `__int64 __fastcall(CWcnPageProfileCreateNew *__hidden this, HWND, unsigned int, unsigned __int64, HWND hWnd, __int64 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000bbc0`
- `0x1800143ac`
- `0x1800144e4`
- `0x1800146b0`
- `0x180015498`
- `0x180015b1c`
- `0x180016008`

## import_xrefs

- `USER32!SendMessageW` at `0x18000bd2a`
- `USER32!SendMessageW` at `0x18000bdc7`
- `USER32!SendMessageW` at `0x18000bd2a`
- `USER32!SendMessageW` at `0x18000bdc7`

## pseudocode

```c
__int64 __fastcall CWcnPageProfileCreateNew::ProcessWindowMessage(
        CWcnPageProfileCreateNew *this,
        HWND a2,
        __int64 a3,
        HWND a4,
        HWND hWnd,
        __int64 *a6,
        unsigned int a7)
{
  char *v8; // rbx
  CWcnPageProfileCreateNew *v9; // rcx
  unsigned int SelectedItemHelper; // eax
  HWND v11; // rdx
  CWcnPageProfileCreateNew *v12; // rcx
  HWND *v14; // rbx
  unsigned int v15; // eax
  HWND v16; // rdx
  CWcnPageProfileCreateNew *v17; // rcx
  int v18; // eax

  if ( !a7 )
  {
    if ( (_DWORD)a3 == 273 )
    {
      if ( (_DWORD)a4 == 67138 )
      {
        v8 = (char *)this - 176;
        if ( !*((_BYTE *)this + 490) )
          v8[665] = 1;
        *((_DWORD *)v8 + 51) = -1;
        CWcnPageProfileCreateNew::PopulateCipherTypesList((HWND *)v8);
        SelectedItemHelper = CWcnPageProfileCreateNew::GetSelectedItemHelper(v9, *((HWND *)v8 + 41));
        v11 = (HWND)*((_QWORD *)v8 + 43);
        v12 = (CWcnPageProfileCreateNew *)*(unsigned int *)&byte_1800369E0[28 * SelectedItemHelper + 16];
        *((_DWORD *)v8 + 50) = (_DWORD)v12;
        *((_DWORD *)v8 + 51) = *(_DWORD *)&byte_1800369E0[28 * CWcnPageProfileCreateNew::GetSelectedItemHelper(v12, v11)
                                                        + 20];
        *a6 = 0;
        return 1;
      }
      if ( (_WORD)a4 == 1603 )
      {
        if ( WORD1(a4) == 1 )
        {
          v14 = (HWND *)((char *)this - 176);
          if ( !*((_BYTE *)this + 490) )
            *((_BYTE *)v14 + 665) = 1;
          v15 = CWcnPageProfileCreateNew::GetSelectedItemHelper(
                  (CWcnPageProfileCreateNew *)((unsigned __int64)a4 >> 16),
                  v14[41]);
          v16 = v14[43];
          *((_DWORD *)v14 + 50) = *(_DWORD *)&byte_1800369E0[28 * v15 + 16];
          *((_DWORD *)v14 + 51) = *(_DWORD *)&byte_1800369E0[28
                                                           * CWcnPageProfileCreateNew::GetSelectedItemHelper(v17, v16)
                                                           + 20];
          CWcnPageProfileCreateNew::UpdateSecurityDisplayInformation(v14);
          goto LABEL_13;
        }
      }
      else if ( (_DWORD)a4 == 2918 )
      {
        v18 = SendMessageW(hWnd, 0xF0u, 0, 0);
        CWcnPageProfileCreateNew::SetLowerPaneActive((CWcnPageProfileCreateNew *)((char *)this - 176), v18 == 1);
LABEL_13:
        *a6 = 0;
        return 1;
      }
      if ( (_DWORD)a4 == 50333059 )
      {
        *a6 = CWcnPageProfileCreateNew::OnEditSsid((CWcnPageProfileCreateNew *)((char *)this - 176), 768, a3, a4);
        return 1;
      }
      if ( (_WORD)a4 == 1412 )
      {
        if ( WORD1(a4) == 768 )
        {
          if ( !*((_BYTE *)this + 490) )
            *((_BYTE *)this + 489) = 1;
          goto LABEL_13;
        }
        return 0;
      }
      if ( (_DWORD)a4 == 2304 )
      {
        *((_BYTE *)this + 185) = (unsigned int)SendMessageW(hWnd, 0xF0u, 0, 0) == 1;
        goto LABEL_13;
      }
    }
    else if ( (_DWORD)a3 == 78 && *((_QWORD *)hWnd + 1) == 2012 && (unsigned int)(*((_DWORD *)hWnd + 4) + 4) <= 2 )
    {
      CWcnPageProfileCreateNew::OnClickLinkToExistingProfile((CWcnPageProfileCreateNew *)((char *)this - 176));
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000bbc0  mov     [rsp+arg_0], rbx
0x18000bbc5  mov     [rsp+arg_8], rsi
0x18000bbca  push    rdi
0x18000bbcb  sub     rsp, 30h
0x18000bbcf  cmp     [rsp+38h+arg_30], 0
0x18000bbd4  mov     rbx, rcx
0x18000bbd7  jnz     loc_18000BE10
0x18000bbdd  cmp     r8d, 111h
0x18000bbe4  jnz     loc_18000BDDD
0x18000bbea  mov     rcx, r9
0x18000bbed  mov     eax, 642h
0x18000bbf2  shr     rcx, 10h; this
0x18000bbf6  mov     edi, 1
0x18000bbfb  cmp     ax, r9w
0x18000bbff  jnz     loc_18000BC85
0x18000bc05  cmp     di, cx
0x18000bc08  jnz     short loc_18000BC85
0x18000bc0a  add     rbx, 0FFFFFFFFFFFFFF50h
0x18000bc11  cmp     byte ptr [rbx+29Ah], 0
0x18000bc18  jnz     short loc_18000BC21
0x18000bc1a  mov     [rbx+299h], dil
0x18000bc21  mov     rcx, rbx; this
0x18000bc24  mov     dword ptr [rbx+0CCh], 0FFFFFFFFh
0x18000bc2e  call    ?PopulateCipherTypesList@CWcnPageProfileCreateNew@@AEAAXXZ; CWcnPageProfileCreateNew::PopulateCipherTypesList(void)
0x18000bc33  mov     rdx, [rbx+148h]; HWND
0x18000bc3a  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x18000bc3f  mov     rdx, [rbx+158h]; HWND
0x18000bc46  lea     rsi, byte_1800369E0
0x18000bc4d  mov     eax, eax
0x18000bc4f  imul    rcx, rax, 1Ch
0x18000bc53  mov     ecx, [rcx+rsi+10h]; this
0x18000bc57  mov     [rbx+0C8h], ecx
0x18000bc5d  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x18000bc62  mov     ecx, eax
0x18000bc64  imul    rcx, 1Ch
0x18000bc68  mov     ecx, [rcx+rsi+14h]
0x18000bc6c  mov     [rbx+0CCh], ecx
0x18000bc72  mov     rcx, [rsp+38h+arg_28]
0x18000bc77  mov     qword ptr [rcx], 0
0x18000bc7e  mov     eax, edi
0x18000bc80  jmp     loc_18000BE12
0x18000bc85  mov     eax, 643h
0x18000bc8a  cmp     ax, r9w
0x18000bc8e  jnz     short loc_18000BD08
0x18000bc90  cmp     di, cx
0x18000bc93  jnz     loc_18000BD43
0x18000bc99  add     rbx, 0FFFFFFFFFFFFFF50h
0x18000bca0  cmp     byte ptr [rbx+29Ah], 0
0x18000bca7  jnz     short loc_18000BCB0
0x18000bca9  mov     [rbx+299h], dil
0x18000bcb0  mov     rdx, [rbx+148h]; HWND
0x18000bcb7  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x18000bcbc  mov     rdx, [rbx+158h]; HWND
0x18000bcc3  lea     rsi, byte_1800369E0
0x18000bcca  mov     eax, eax
0x18000bccc  imul    rax, 1Ch
0x18000bcd0  mov     eax, [rax+rsi+10h]
0x18000bcd4  mov     [rbx+0C8h], eax
0x18000bcda  call    ?GetSelectedItemHelper@CWcnPageProfileCreateNew@@AEBAIPEAUHWND__@@@Z; CWcnPageProfileCreateNew::GetSelectedItemHelper(HWND__ *)
0x18000bcdf  mov     eax, eax
0x18000bce1  mov     rcx, rbx; this
0x18000bce4  imul    rax, 1Ch
0x18000bce8  mov     eax, [rax+rsi+14h]
0x18000bcec  mov     [rbx+0CCh], eax
0x18000bcf2  call    ?UpdateSecurityDisplayInformation@CWcnPageProfileCreateNew@@AEAAXXZ; CWcnPageProfileCreateNew::UpdateSecurityDisplayInformation(void)
0x18000bcf7  mov     rax, [rsp+38h+arg_28]
0x18000bcfc  mov     qword ptr [rax], 0
0x18000bd03  jmp     loc_18000BC7E
0x18000bd08  mov     eax, 0B66h
0x18000bd0d  cmp     ax, r9w
0x18000bd11  jnz     short loc_18000BD43
0x18000bd13  xor     eax, eax
0x18000bd15  cmp     ax, cx
0x18000bd18  jnz     short loc_18000BD43
0x18000bd1a  mov     rcx, [rsp+38h+hWnd]; hWnd
0x18000bd1f  xor     r9d, r9d; lParam
0x18000bd22  xor     r8d, r8d; wParam
0x18000bd25  mov     edx, 0F0h; Msg
0x18000bd2a  call    cs:__imp_SendMessageW
0x18000bd30  cmp     eax, edi
0x18000bd32  lea     rcx, [rbx-0B0h]; this
0x18000bd39  setz    dl; bool
0x18000bd3c  call    ?SetLowerPaneActive@CWcnPageProfileCreateNew@@AEAAX_N@Z; CWcnPageProfileCreateNew::SetLowerPaneActive(bool)
0x18000bd41  jmp     short loc_18000BCF7
0x18000bd43  mov     rcx, r9
0x18000bd46  mov     eax, 583h
0x18000bd4b  shr     rcx, 10h
0x18000bd4f  mov     edx, 300h; unsigned __int16
0x18000bd54  cmp     ax, r9w
0x18000bd58  jnz     short loc_18000BD78
0x18000bd5a  cmp     dx, cx
0x18000bd5d  jnz     short loc_18000BD78
0x18000bd5f  lea     rcx, [rbx-0B0h]; this
0x18000bd66  call    ?OnEditSsid@CWcnPageProfileCreateNew@@QEAA_JGGPEAUHWND__@@AEAH@Z; CWcnPageProfileCreateNew::OnEditSsid(ushort,ushort,HWND__ *,int &)
0x18000bd6b  mov     rcx, [rsp+38h+arg_28]
0x18000bd70  mov     [rcx], rax
0x18000bd73  jmp     loc_18000BC7E
0x18000bd78  mov     eax, 584h
0x18000bd7d  cmp     ax, r9w
0x18000bd81  jnz     short loc_18000BDA5
0x18000bd83  cmp     dx, cx
0x18000bd86  jnz     loc_18000BE10
0x18000bd8c  cmp     byte ptr [rbx+1EAh], 0
0x18000bd93  jnz     loc_18000BCF7
0x18000bd99  mov     [rbx+1E9h], dil
0x18000bda0  jmp     loc_18000BCF7
0x18000bda5  mov     eax, 900h
0x18000bdaa  cmp     ax, r9w
0x18000bdae  jnz     short loc_18000BE10
0x18000bdb0  xor     eax, eax
0x18000bdb2  cmp     ax, cx
0x18000bdb5  jnz     short loc_18000BE10
0x18000bdb7  mov     rcx, [rsp+38h+hWnd]; hWnd
0x18000bdbc  xor     r9d, r9d; lParam
0x18000bdbf  xor     r8d, r8d; wParam
0x18000bdc2  mov     edx, 0F0h; Msg
0x18000bdc7  call    cs:__imp_SendMessageW
0x18000bdcd  cmp     eax, edi
0x18000bdcf  setz    al
0x18000bdd2  mov     [rbx+0B9h], al
0x18000bdd8  jmp     loc_18000BCF7
0x18000bddd  cmp     r8d, 4Eh ; 'N'
0x18000bde1  jnz     short loc_18000BE10
0x18000bde3  mov     rax, [rsp+38h+hWnd]
0x18000bde8  cmp     qword ptr [rax+8], 7DCh
0x18000bdf0  jnz     short loc_18000BE10
0x18000bdf2  mov     eax, [rax+10h]
0x18000bdf5  add     eax, 4
0x18000bdf8  cmp     eax, 2
0x18000bdfb  ja      short loc_18000BE10
0x18000bdfd  add     rcx, 0FFFFFFFFFFFFFF50h; this
0x18000be04  call    ?OnClickLinkToExistingProfile@CWcnPageProfileCreateNew@@QEAAXXZ; CWcnPageProfileCreateNew::OnClickLinkToExistingProfile(void)
0x18000be09  mov     eax, 1
0x18000be0e  jmp     short loc_18000BE12
0x18000be10  xor     eax, eax
0x18000be12  mov     rbx, [rsp+38h+arg_0]
0x18000be17  mov     rsi, [rsp+38h+arg_8]
0x18000be1c  add     rsp, 30h
0x18000be20  pop     rdi
0x18000be21  retn
```
