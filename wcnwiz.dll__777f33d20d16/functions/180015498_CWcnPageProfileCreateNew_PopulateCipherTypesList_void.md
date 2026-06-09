# CWcnPageProfileCreateNew::PopulateCipherTypesList(void)

- ea: `0x180015498`
- end: `0x1800156b8`
- name: `?PopulateCipherTypesList@CWcnPageProfileCreateNew@@AEAAXXZ`
- size: `544`
- prototype: `void __fastcall(CWcnPageProfileCreateNew *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000bbc0`
- `0x18001515c`

## callees

- `0x180001820`
- `0x18000d630`
- `0x18000e19c`
- `0x1800143fc`
- `0x180014784`
- `0x180015498`
- `0x180016008`
- `0x18002de1c`

## import_xrefs

- `USER32!SendMessageW` at `0x180015512`
- `USER32!SendMessageW` at `0x18001552a`
- `USER32!SendMessageW` at `0x180015542`
- `USER32!SendMessageW` at `0x1800155c2`
- `USER32!SendMessageW` at `0x1800155dd`
- `USER32!SendMessageW` at `0x180015602`
- `USER32!SendMessageW` at `0x180015512`
- `USER32!SendMessageW` at `0x18001552a`
- `USER32!SendMessageW` at `0x180015542`
- `USER32!SendMessageW` at `0x1800155c2`
- `USER32!SendMessageW` at `0x1800155dd`
- `USER32!SendMessageW` at `0x180015602`

## pseudocode

```c
void __fastcall CWcnPageProfileCreateNew::PopulateCipherTypesList(HWND *this)
{
  int v2; // edi
  int v3; // esi
  const char *Indent; // rax
  __int64 v5; // r10
  int v6; // eax
  LRESULT v7; // rax
  unsigned int v8; // r9d
  signed int v9; // ebp
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  char v12; // r8
  int v13; // r14d
  int v14; // r13d
  int DecoratedString; // eax
  int v16; // eax
  unsigned int v17; // [rsp+30h] [rbp-168h]
  unsigned __int16 lParam[128]; // [rsp+40h] [rbp-158h] BYREF

  v2 = 4357;
  v3 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 44, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids, Indent);
  }
  SendMessageW(this[43], 0x14Bu, 0, 0);
  v6 = SendMessageW(this[41], 0x147u, 0, 0);
  v7 = SendMessageW(this[41], 0x150u, v6, 0);
  v9 = 0;
  v10 = *(unsigned int *)&byte_1800369E0[28 * v7 + 16];
  v17 = *(_DWORD *)&byte_1800369E0[28 * v7 + 16];
  while ( (unsigned int)v9 < 3 )
  {
    v11 = 28LL * v9;
    if ( *(_DWORD *)&byte_1800369E0[v11 + 16] == (_DWORD)v10 )
    {
      v12 = byte_1800369E0[v11 + 8];
      v13 = *(_DWORD *)&byte_1800369E0[v11 + 4];
      if ( v12 || (v13 & *((_DWORD *)this + 53)) != 0 )
      {
        v14 = *(_DWORD *)&byte_1800369E0[v11 + 20];
        DecoratedString = CWcnPageProfileCreateNew::LoadDecoratedString(
                            (CWcnPageProfileCreateNew *)v10,
                            v14,
                            v12,
                            v8,
                            lParam);
        if ( DecoratedString < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              45,
              WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids,
              (unsigned int)DecoratedString);
          return;
        }
        SendMessageW(this[43], 0x143u, 0, (LPARAM)lParam);
        SendMessageW(this[43], 0x151u, v3, v9);
        if ( v14 == *((_DWORD *)this + 51) || !v3 )
        {
          SendMessageW(this[43], 0x14Eu, v3, 0);
          v2 = v13;
        }
        v10 = v17;
        ++v3;
      }
    }
    ++v9;
  }
  v16 = *((_DWORD *)this + 52);
  if ( v16 != v2 && (v16 != 8 || v2 != 4) && (v16 != 4 || v2 != 8) )
  {
    *((_DWORD *)this + 52) = v2;
    *((_BYTE *)this + 666) = 1;
    CWcnPageProfileCreateNew::OnGenNewKey((CWcnPageProfileCreateNew *)this);
    *((_BYTE *)this + 666) = 0;
  }
  CWcnPageProfileCreateNew::UpdateSecurityDisplayInformation(this);
}

```

## disassembly

```asm
0x180015498  push    rbx
0x18001549a  push    rbp
0x18001549b  push    rsi
0x18001549c  push    rdi
0x18001549d  push    r12
0x18001549f  push    r13
0x1800154a1  push    r14
0x1800154a3  push    r15
0x1800154a5  sub     rsp, 158h
0x1800154ac  mov     rax, cs:__security_cookie
0x1800154b3  xor     rax, rsp
0x1800154b6  mov     [rsp+198h+var_58], rax
0x1800154be  mov     rbx, rcx
0x1800154c1  mov     edi, 1105h
0x1800154c6  xor     esi, esi
0x1800154c8  mov     r10, cs:WPP_GLOBAL_Control
0x1800154cf  lea     r12, WPP_GLOBAL_Control
0x1800154d6  cmp     r10, r12
0x1800154d9  jz      short loc_180015500
0x1800154db  cmp     byte ptr [r10+19h], 6
0x1800154e0  jb      short loc_180015500
0x1800154e2  lea     ecx, [rsi+1]; int
0x1800154e5  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800154ea  mov     rcx, [r10+10h]
0x1800154ee  lea     edx, [rsi+2Ch]
0x1800154f1  mov     r9, rax
0x1800154f4  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x1800154fb  call    WPP_SF_s
0x180015500  mov     rcx, [rbx+158h]; hWnd
0x180015507  xor     r9d, r9d; lParam
0x18001550a  xor     r8d, r8d; wParam
0x18001550d  mov     edx, 14Bh; Msg
0x180015512  call    cs:__imp_SendMessageW
0x180015518  mov     rcx, [rbx+148h]; hWnd
0x18001551f  xor     r9d, r9d; lParam
0x180015522  xor     r8d, r8d; wParam
0x180015525  mov     edx, 147h; Msg
0x18001552a  call    cs:__imp_SendMessageW
0x180015530  mov     rcx, [rbx+148h]; hWnd
0x180015537  xor     r9d, r9d; lParam
0x18001553a  movsxd  r8, eax; wParam
0x18001553d  mov     edx, 150h; Msg
0x180015542  call    cs:__imp_SendMessageW
0x180015548  imul    rcx, rax, 1Ch
0x18001554c  lea     rdx, byte_1800369E0
0x180015553  xor     ebp, ebp
0x180015555  mov     ecx, [rcx+rdx+10h]; this
0x180015559  mov     [rsp+198h+var_168], ecx
0x18001555d  cmp     ebp, 3
0x180015560  jnb     loc_180015652
0x180015566  movsxd  r15, ebp
0x180015569  imul    rax, r15, 1Ch
0x18001556d  cmp     [rax+rdx+10h], ecx
0x180015571  jnz     loc_180015618
0x180015577  mov     r8b, [rax+rdx+8]; bool
0x18001557c  mov     r14d, [rax+rdx+4]
0x180015581  test    r8b, r8b
0x180015584  jnz     short loc_180015593
0x180015586  test    [rbx+0D4h], r14d
0x18001558d  jz      loc_180015618
0x180015593  mov     r13d, [rax+rdx+14h]
0x180015598  lea     rax, [rsp+198h+lParam]
0x18001559d  mov     edx, r13d; int
0x1800155a0  mov     [rsp+198h+var_178], rax; unsigned __int16 *
0x1800155a5  call    ?LoadDecoratedString@CWcnPageProfileCreateNew@@AEAAJH_NKPEAG@Z; CWcnPageProfileCreateNew::LoadDecoratedString(int,bool,ulong,ushort *)
0x1800155aa  test    eax, eax
0x1800155ac  js      short loc_18001561F
0x1800155ae  mov     rcx, [rbx+158h]; hWnd
0x1800155b5  lea     r9, [rsp+198h+lParam]; lParam
0x1800155ba  xor     r8d, r8d; wParam
0x1800155bd  mov     edx, 143h; Msg
0x1800155c2  call    cs:__imp_SendMessageW
0x1800155c8  mov     rcx, [rbx+158h]; hWnd
0x1800155cf  mov     r9, r15; lParam
0x1800155d2  movsxd  r12, esi
0x1800155d5  mov     edx, 151h; Msg
0x1800155da  mov     r8, r12; wParam
0x1800155dd  call    cs:__imp_SendMessageW
0x1800155e3  cmp     r13d, [rbx+0CCh]
0x1800155ea  jz      short loc_1800155F0
0x1800155ec  test    esi, esi
0x1800155ee  jnz     short loc_18001560B
0x1800155f0  mov     rcx, [rbx+158h]; hWnd
0x1800155f7  xor     r9d, r9d; lParam
0x1800155fa  mov     r8, r12; wParam
0x1800155fd  mov     edx, 14Eh; Msg
0x180015602  call    cs:__imp_SendMessageW
0x180015608  mov     edi, r14d
0x18001560b  mov     ecx, [rsp+198h+var_168]
0x18001560f  lea     rdx, byte_1800369E0
0x180015616  inc     esi
0x180015618  inc     ebp
0x18001561a  jmp     loc_18001555D
0x18001561f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015626  lea     rdx, WPP_GLOBAL_Control
0x18001562d  cmp     rcx, rdx
0x180015630  jz      short loc_180015694
0x180015632  cmp     byte ptr [rcx+19h], 2
0x180015636  jb      short loc_180015694
0x180015638  mov     rcx, [rcx+10h]
0x18001563c  lea     r8, WPP_6921b1fb36713887b950c598bef5eb1a_Traceguids
0x180015643  mov     edx, 2Dh ; '-'
0x180015648  mov     r9d, eax
0x18001564b  call    WPP_SF_d
0x180015650  jmp     short loc_180015694
0x180015652  mov     eax, [rbx+0D0h]
0x180015658  cmp     eax, edi
0x18001565a  jz      short loc_18001568C
0x18001565c  cmp     eax, 8
0x18001565f  jnz     short loc_180015666
0x180015661  cmp     edi, 4
0x180015664  jz      short loc_18001568C
0x180015666  cmp     eax, 4
0x180015669  jnz     short loc_180015670
0x18001566b  cmp     edi, 8
0x18001566e  jz      short loc_18001568C
0x180015670  mov     rcx, rbx; this
0x180015673  mov     [rbx+0D0h], edi
0x180015679  mov     byte ptr [rbx+29Ah], 1
0x180015680  call    ?OnGenNewKey@CWcnPageProfileCreateNew@@QEAAXXZ; CWcnPageProfileCreateNew::OnGenNewKey(void)
0x180015685  mov     byte ptr [rbx+29Ah], 0
0x18001568c  mov     rcx, rbx; this
0x18001568f  call    ?UpdateSecurityDisplayInformation@CWcnPageProfileCreateNew@@AEAAXXZ; CWcnPageProfileCreateNew::UpdateSecurityDisplayInformation(void)
0x180015694  mov     rcx, [rsp+198h+var_58]
0x18001569c  xor     rcx, rsp; StackCookie
0x18001569f  call    __security_check_cookie
0x1800156a4  add     rsp, 158h
0x1800156ab  pop     r15
0x1800156ad  pop     r14
0x1800156af  pop     r13
0x1800156b1  pop     r12
0x1800156b3  pop     rdi
0x1800156b4  pop     rsi
0x1800156b5  pop     rbp
0x1800156b6  pop     rbx
0x1800156b7  retn
```
