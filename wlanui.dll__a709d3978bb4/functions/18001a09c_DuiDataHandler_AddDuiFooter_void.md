# DuiDataHandler::AddDuiFooter(void)

- ea: `0x18001a09c`
- end: `0x18001a657`
- name: `?AddDuiFooter@DuiDataHandler@@AEAAXXZ`
- size: `1467`
- prototype: `void __fastcall(DuiDataHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ab44`

## callees

- `0x180019c58`
- `0x180019da0`
- `0x18001a09c`
- `0x18001a84c`
- `0x18001b324`
- `0x18001bf40`
- `0x18001d010`

## import_xrefs

- `msvcrt!_itow` at `0x18001a26b`
- `msvcrt!_itow` at `0x18001a349`
- `msvcrt!_itow` at `0x18001a3b4`
- `msvcrt!_itow` at `0x18001a41b`
- `msvcrt!_itow` at `0x18001a47b`
- `msvcrt!_itow` at `0x18001a4de`
- `msvcrt!_itow` at `0x18001a5c8`
- `msvcrt!_itow` at `0x18001a605`
- `msvcrt!_itow` at `0x18001a26b`
- `msvcrt!_itow` at `0x18001a349`
- `msvcrt!_itow` at `0x18001a3b4`
- `msvcrt!_itow` at `0x18001a41b`
- `msvcrt!_itow` at `0x18001a47b`
- `msvcrt!_itow` at `0x18001a4de`
- `msvcrt!_itow` at `0x18001a5c8`
- `msvcrt!_itow` at `0x18001a605`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a2ab`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a519`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a2ab`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a519`
- `ole32!CoCreateInstance` at `0x18001a125`
- `ole32!CoCreateInstance` at `0x18001a125`
- `USER32!GetSystemMetrics` at `0x18001a584`
- `USER32!GetSystemMetrics` at `0x18001a591`
- `USER32!GetSystemMetrics` at `0x18001a584`
- `USER32!GetSystemMetrics` at `0x18001a591`

## string_xrefs

- `0x18001a628`: `        </element>    </element></duixml>`
- `0x18001a0ea`: `          <element layoutpos="ninebottom" layout="borderlayout()"  width="%topelementwidth" height="%topelementheight"  background="argb(0,0,0,0)" >%eapcredsCapsAreaSSOPlaceholder          </element>          </element>         </element>        </element>    </element>    <stylesheets>          <!-- Style Sheet for the User List and User Tiles -->        <style resid = "UsersStyle">          <if visible = "false">              <element                  width = "0rp"                  height = "0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DuiDataHandler::AddDuiFooter(DuiDataHandler *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  wchar_t *v4; // rdi
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // r12
  __int64 v8; // r13
  void *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int SystemMetrics; // ebx
  int v13; // edi
  int v14; // [rsp+30h] [rbp-69h] BYREF
  __int64 v15; // [rsp+38h] [rbp-61h]
  LPVOID ppv; // [rsp+40h] [rbp-59h] BYREF
  void *v17; // [rsp+48h] [rbp-51h]
  __int64 v18; // [rsp+58h] [rbp-41h]
  unsigned __int64 v19; // [rsp+60h] [rbp-39h]
  wchar_t Buffer[8]; // [rsp+68h] [rbp-31h] BYREF
  int v21; // [rsp+78h] [rbp-21h]
  wchar_t v22[8]; // [rsp+80h] [rbp-19h] BYREF
  __int128 v23; // [rsp+90h] [rbp-9h]
  __int64 v24; // [rsp+A0h] [rbp+7h]

  v2 = *((_QWORD *)this + 3);
  if ( !v2 || (v3 = *(_QWORD *)(v2 + 8)) == 0 || *(_DWORD *)(v3 + 20) != 1 )
  {
    std::wstring::operator+=(*(void **)this, L"        </element>    </element></duixml>");
    return;
  }
  std::wstring::operator+=(*(void **)this, aElementLayoutp_0);
  v14 = 0;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_AuthUIBackground, 0, 1u, &GUID_6f7aef3e_2780_4a3f_82c3_5c078663af2a, &ppv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 32LL))(ppv, &v14);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( !v14 )
    goto LABEL_11;
  if ( v14 == 1 )
  {
    v4 = L"130";
    v5 = 156;
    v6 = 108;
    v7 = 120;
    v8 = 132;
    v15 = 144;
    goto LABEL_13;
  }
  if ( v14 != 2 )
  {
LABEL_11:
    v15 = 140;
    v8 = 128;
    v7 = 116;
    v6 = 104;
    v5 = 152;
    v4 = L"0";
    goto LABEL_13;
  }
  v4 = L"45";
  v5 = 160;
  v6 = 112;
  v7 = 124;
  v8 = 136;
  v15 = 148;
LABEL_13:
  while ( 1 )
  {
    v9 = *(void **)this;
    if ( std::wstring::find(*(_QWORD *)this, L"%4") == -1 )
      break;
    DuiStringFindAndReplace(v9, (__int64)L"%4", v4);
  }
  v10 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL);
  if ( *(_DWORD *)(v10 + 72) && *(_DWORD *)(v10 + 80) && *(_DWORD *)(v10 + 76) && *(_QWORD *)(v10 + 88) )
  {
    DuiStringFindAndReplace(
      v9,
      (__int64)L"%editcontrolbackground",
      L"background = \"graphic(%1, 7,-1,0,0,1,1,library(%2))\" ");
    v19 = 7;
    v18 = 0;
    LOWORD(v17) = 0;
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    _itow(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 80LL), Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", Buffer);
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%2",
      *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 88LL));
    if ( v19 >= 8 )
      operator delete(v17);
  }
  else
  {
    DuiStringFindAndReplace(v9, (__int64)L"%editcontrolbackground", L"background = \"argb(0,0,0,0)\" ");
  }
  v11 = *(_QWORD *)(*((_QWORD *)this + 3) + 8LL);
  if ( *(_DWORD *)(v11 + 96) && *(_DWORD *)(v11 + 100) && *(_QWORD *)(v11 + 168) )
  {
    v19 = 7;
    v18 = 0;
    LOWORD(v17) = 0;
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%buttoncontrolbackgroundrest",
      L"background = \"graphic(%1,7,-1,0,0,1,1,library(%2))\" ");
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    _itow(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + v5), Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", Buffer);
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%2",
      *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 168LL));
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%buttoncontrolbackgroundkey",
      L"background = \"graphic(%1,7,-1,0,0,1,1,library(%2))\" ");
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    _itow(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + v6), Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", Buffer);
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%2",
      *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 168LL));
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%buttoncontrolbackgroundmouse",
      L"background = \"graphic(%1,7,-1,0,0,1,1,library(%2))\" ");
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    _itow(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + v7), Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", Buffer);
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%2",
      *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 168LL));
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%buttoncontrolbackgroundboth",
      L"background = \"graphic(%1,7,-1,0,0,1,1,library(%2))\" ");
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    _itow(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + v8), Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", Buffer);
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%2",
      *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 168LL));
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%buttoncontrolbackgroundpress",
      L"background = \"graphic(%1,7,-1,0,0,1,1,library(%2))\" ");
    *(_OWORD *)Buffer = 0;
    v21 = 0;
    _itow(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + v15), Buffer, 10);
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%1", Buffer);
    DuiStringFindAndReplace(
      *(void **)this,
      (__int64)L"%2",
      *(_WORD **)(*(_QWORD *)(*((_QWORD *)this + 3) + 8LL) + 168LL));
    if ( v19 >= 8 )
      operator delete(v17);
  }
  else
  {
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%buttoncontrolbackgroundmouse", L"background = \"blue\" ");
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%buttoncontrolbackgroundkey", L"background = \"blue\" ");
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%buttoncontrolbackgroundboth", L"background = \"blue\" ");
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%buttoncontrolbackgroundpress", L"background = \"blue\" ");
    DuiStringFindAndReplace(*(void **)this, (__int64)L"%buttoncontrolbackgroundrest", L"background = \"blue\" ");
  }
  SystemMetrics = GetSystemMetrics(0);
  v13 = GetSystemMetrics(1);
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  _itow(SystemMetrics / 3, v22, 10);
  DuiStringFindAndReplace(*(void **)this, (__int64)L"%topelementwidth", v22);
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  _itow(v13 / 3, v22, 10);
  DuiStringFindAndReplace(*(void **)this, (__int64)L"%topelementheight", v22);
  DuiDataHandler::AddDuiCapsLockArea(this);
}

```

## disassembly

```asm
0x18001a09c  push    rbp
0x18001a09e  push    rbx
0x18001a09f  push    rsi
0x18001a0a0  push    rdi
0x18001a0a1  push    r12
0x18001a0a3  push    r13
0x18001a0a5  push    r14
0x18001a0a7  push    r15
0x18001a0a9  lea     rbp, [rsp-1Fh]
0x18001a0ae  sub     rsp, 0B8h
0x18001a0b5  mov     rax, cs:__security_cookie
0x18001a0bc  xor     rax, rsp
0x18001a0bf  mov     [rbp+57h+var_48], rax
0x18001a0c3  mov     rsi, rcx
0x18001a0c6  mov     rax, [rcx+18h]
0x18001a0ca  test    rax, rax
0x18001a0cd  jz      loc_18001A628
0x18001a0d3  mov     rax, [rax+8]
0x18001a0d7  test    rax, rax
0x18001a0da  jz      loc_18001A628
0x18001a0e0  cmp     dword ptr [rax+14h], 1
0x18001a0e4  jnz     loc_18001A628
0x18001a0ea  lea     rdx, aElementLayoutp_0; "          <element layoutpos=\"ninebott"...
0x18001a0f1  mov     rcx, [rcx]; Src
0x18001a0f4  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x18001a0f9  mov     [rbp+57h+var_C0], 0
0x18001a100  mov     [rbp+57h+var_B0], 0
0x18001a108  lea     rax, [rbp+57h+var_B0]
0x18001a10c  mov     [rsp+0F0h+ppv], rax; ppv
0x18001a111  lea     r9, _GUID_6f7aef3e_2780_4a3f_82c3_5c078663af2a; riid
0x18001a118  xor     edx, edx; pUnkOuter
0x18001a11a  lea     r8d, [rdx+1]; dwClsContext
0x18001a11e  lea     rcx, CLSID_AuthUIBackground; rclsid
0x18001a125  call    cs:__imp_CoCreateInstance
0x18001a12b  test    eax, eax
0x18001a12d  js      short loc_18001A153
0x18001a12f  mov     rcx, [rbp+57h+var_B0]
0x18001a133  mov     rax, [rcx]
0x18001a136  lea     rdx, [rbp+57h+var_C0]
0x18001a13a  mov     rax, [rax+20h]
0x18001a13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a143  mov     rcx, [rbp+57h+var_B0]
0x18001a147  mov     rax, [rcx]
0x18001a14a  mov     rax, [rax+10h]
0x18001a14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a153  mov     eax, [rbp+57h+var_C0]
0x18001a156  test    eax, eax
0x18001a158  jz      short loc_18001A1AA
0x18001a15a  sub     eax, 1
0x18001a15d  jz      short loc_18001A187
0x18001a15f  cmp     eax, 1
0x18001a162  jnz     short loc_18001A1AA
0x18001a164  lea     rdi, a45; "45"
0x18001a16b  mov     r14d, 0A0h
0x18001a171  lea     r15d, [rax+6Fh]
0x18001a175  lea     r12d, [rax+7Bh]
0x18001a179  lea     r13d, [r14-18h]
0x18001a17d  mov     [rbp+57h+var_B8], 94h
0x18001a185  jmp     short loc_18001A1DF
0x18001a187  lea     rdi, a130; "130"
0x18001a18e  mov     r14d, 9Ch
0x18001a194  lea     r15d, [r14-30h]
0x18001a198  lea     r12d, [r14-24h]
0x18001a19c  lea     r13d, [r14-18h]
0x18001a1a0  mov     [rbp+57h+var_B8], 90h
0x18001a1a8  jmp     short loc_18001A1DF
0x18001a1aa  mov     [rbp+57h+var_B8], 8Ch
0x18001a1b2  mov     r13d, 80h
0x18001a1b8  lea     r12d, [r13-0Ch]
0x18001a1bc  lea     r15d, [r13-18h]
0x18001a1c0  lea     r14d, [r13+18h]
0x18001a1c4  lea     rdi, a0; "0"
0x18001a1cb  jmp     short loc_18001A1DF
0x18001a1cd  mov     r8, rdi
0x18001a1d0  lea     rdx, a4; "%4"
0x18001a1d7  mov     rcx, rbx; Src
0x18001a1da  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a1df  mov     rbx, [rsi]
0x18001a1e2  lea     rdx, a4; "%4"
0x18001a1e9  mov     rcx, rbx
0x18001a1ec  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K@Z; std::wstring::find(ushort const *,unsigned __int64)
0x18001a1f1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a1f5  jnz     short loc_18001A1CD
0x18001a1f7  mov     rax, [rsi+18h]
0x18001a1fb  mov     rcx, [rax+8]
0x18001a1ff  xor     edi, edi
0x18001a201  cmp     [rcx+48h], edi
0x18001a204  jz      loc_18001A2B3
0x18001a20a  cmp     [rcx+50h], edi
0x18001a20d  jbe     loc_18001A2B3
0x18001a213  cmp     [rcx+4Ch], edi
0x18001a216  jz      loc_18001A2B3
0x18001a21c  cmp     [rcx+58h], rdi
0x18001a220  jz      loc_18001A2B3
0x18001a226  lea     r8, aBackgroundGrap; "background = \"graphic(%1, 7,-1,0,0,1,1"...
0x18001a22d  lea     rdx, aEditcontrolbac; "%editcontrolbackground"
0x18001a234  mov     rcx, rbx; Src
0x18001a237  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a23c  mov     [rbp+57h+var_90], 7
0x18001a244  mov     [rbp+57h+var_98], rdi
0x18001a248  mov     word ptr [rbp+57h+var_A8], di
0x18001a24c  xorps   xmm0, xmm0
0x18001a24f  xor     eax, eax
0x18001a251  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a255  mov     [rbp+57h+var_78], eax
0x18001a258  mov     rax, [rsi+18h]
0x18001a25c  mov     rcx, [rax+8]
0x18001a260  lea     r8d, [rdi+0Ah]; Radix
0x18001a264  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a268  mov     ecx, [rcx+50h]; Value
0x18001a26b  call    cs:__imp__itow
0x18001a271  lea     r8, [rbp+57h+Buffer]
0x18001a275  lea     rdx, a1; "%1"
0x18001a27c  mov     rcx, [rsi]; Src
0x18001a27f  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a284  mov     rax, [rsi+18h]
0x18001a288  mov     r8, [rax+8]
0x18001a28c  mov     r8, [r8+58h]
0x18001a290  lea     rdx, a2; "%2"
0x18001a297  mov     rcx, [rsi]; Src
0x18001a29a  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a29f  nop
0x18001a2a0  cmp     [rbp+57h+var_90], 8
0x18001a2a5  jb      short loc_18001A2C9
0x18001a2a7  mov     rcx, [rbp+57h+var_A8]
0x18001a2ab  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a2b1  jmp     short loc_18001A2C9
0x18001a2b3  lea     r8, aBackgroundArgb; "background = \"argb(0,0,0,0)\" "
0x18001a2ba  lea     rdx, aEditcontrolbac; "%editcontrolbackground"
0x18001a2c1  mov     rcx, rbx; Src
0x18001a2c4  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a2c9  mov     rax, [rsi+18h]
0x18001a2cd  mov     rcx, [rax+8]
0x18001a2d1  cmp     [rcx+60h], edi
0x18001a2d4  jz      loc_18001A521
0x18001a2da  cmp     [rcx+64h], edi
0x18001a2dd  jz      loc_18001A521
0x18001a2e3  cmp     [rcx+0A8h], rdi
0x18001a2ea  jz      loc_18001A521
0x18001a2f0  mov     [rbp+57h+var_90], 7
0x18001a2f8  mov     [rbp+57h+var_98], rdi
0x18001a2fc  mov     word ptr [rbp+57h+var_A8], di
0x18001a300  xorps   xmm0, xmm0
0x18001a303  xor     eax, eax
0x18001a305  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a309  mov     [rbp+57h+var_78], eax
0x18001a30c  lea     rbx, aBackgroundGrap_0; "background = \"graphic(%1,7,-1,0,0,1,1,"...
0x18001a313  mov     r8, rbx
0x18001a316  lea     rdx, aButtoncontrolb_2; "%buttoncontrolbackgroundrest"
0x18001a31d  mov     rcx, [rsi]; Src
0x18001a320  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a325  xorps   xmm0, xmm0
0x18001a328  xor     eax, eax
0x18001a32a  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a32e  mov     [rbp+57h+var_78], eax
0x18001a331  mov     rax, [rsi+18h]
0x18001a335  mov     rcx, [rax+8]
0x18001a339  mov     edi, 0Ah
0x18001a33e  mov     r8d, edi; Radix
0x18001a341  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a345  mov     ecx, [rcx+r14]; Value
0x18001a349  call    cs:__imp__itow
0x18001a34f  lea     r8, [rbp+57h+Buffer]
0x18001a353  lea     r14, a1; "%1"
0x18001a35a  mov     rdx, r14
0x18001a35d  mov     rcx, [rsi]; Src
0x18001a360  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a365  mov     rax, [rsi+18h]
0x18001a369  mov     r8, [rax+8]
0x18001a36d  mov     r8, [r8+0A8h]
0x18001a374  lea     rdx, a2; "%2"
0x18001a37b  mov     rcx, [rsi]; Src
0x18001a37e  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a383  mov     r8, rbx
0x18001a386  lea     rdx, aButtoncontrolb_3; "%buttoncontrolbackgroundkey"
0x18001a38d  mov     rcx, [rsi]; Src
0x18001a390  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a395  xorps   xmm0, xmm0
0x18001a398  xor     eax, eax
0x18001a39a  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a39e  mov     [rbp+57h+var_78], eax
0x18001a3a1  mov     rax, [rsi+18h]
0x18001a3a5  mov     rcx, [rax+8]
0x18001a3a9  mov     r8d, edi; Radix
0x18001a3ac  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a3b0  mov     ecx, [rcx+r15]; Value
0x18001a3b4  call    cs:__imp__itow
0x18001a3ba  lea     r8, [rbp+57h+Buffer]
0x18001a3be  mov     rdx, r14
0x18001a3c1  mov     rcx, [rsi]; Src
0x18001a3c4  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a3c9  mov     rax, [rsi+18h]
0x18001a3cd  mov     r8, [rax+8]
0x18001a3d1  mov     r8, [r8+0A8h]
0x18001a3d8  lea     r15, a2; "%2"
0x18001a3df  mov     rdx, r15
0x18001a3e2  mov     rcx, [rsi]; Src
0x18001a3e5  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a3ea  mov     r8, rbx
0x18001a3ed  lea     rdx, aButtoncontrolb_1; "%buttoncontrolbackgroundmouse"
0x18001a3f4  mov     rcx, [rsi]; Src
0x18001a3f7  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a3fc  xorps   xmm0, xmm0
0x18001a3ff  xor     eax, eax
0x18001a401  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a405  mov     [rbp+57h+var_78], eax
0x18001a408  mov     rax, [rsi+18h]
0x18001a40c  mov     rcx, [rax+8]
0x18001a410  mov     r8d, edi; Radix
0x18001a413  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a417  mov     ecx, [rcx+r12]; Value
0x18001a41b  call    cs:__imp__itow
0x18001a421  lea     r8, [rbp+57h+Buffer]
0x18001a425  mov     rdx, r14
0x18001a428  mov     rcx, [rsi]; Src
0x18001a42b  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a430  mov     rax, [rsi+18h]
0x18001a434  mov     r8, [rax+8]
0x18001a438  mov     r8, [r8+0A8h]
0x18001a43f  mov     rdx, r15
0x18001a442  mov     rcx, [rsi]; Src
0x18001a445  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a44a  mov     r8, rbx
0x18001a44d  lea     rdx, aButtoncontrolb; "%buttoncontrolbackgroundboth"
0x18001a454  mov     rcx, [rsi]; Src
0x18001a457  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a45c  xorps   xmm0, xmm0
0x18001a45f  xor     eax, eax
0x18001a461  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a465  mov     [rbp+57h+var_78], eax
0x18001a468  mov     rax, [rsi+18h]
0x18001a46c  mov     rcx, [rax+8]
0x18001a470  mov     r8d, edi; Radix
0x18001a473  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a477  mov     ecx, [rcx+r13]; Value
0x18001a47b  call    cs:__imp__itow
0x18001a481  lea     r8, [rbp+57h+Buffer]
0x18001a485  mov     rdx, r14
0x18001a488  mov     rcx, [rsi]; Src
0x18001a48b  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a490  mov     rax, [rsi+18h]
0x18001a494  mov     r8, [rax+8]
0x18001a498  mov     r8, [r8+0A8h]
0x18001a49f  mov     rdx, r15
0x18001a4a2  mov     rcx, [rsi]; Src
0x18001a4a5  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a4aa  mov     r8, rbx
0x18001a4ad  lea     rdx, aButtoncontrolb_0; "%buttoncontrolbackgroundpress"
0x18001a4b4  mov     rcx, [rsi]; Src
0x18001a4b7  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a4bc  xorps   xmm0, xmm0
0x18001a4bf  xor     eax, eax
0x18001a4c1  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18001a4c5  mov     [rbp+57h+var_78], eax
0x18001a4c8  mov     rax, [rsi+18h]
0x18001a4cc  mov     rcx, [rax+8]
0x18001a4d0  mov     r8d, edi; Radix
0x18001a4d3  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001a4d7  mov     rax, [rbp+57h+var_B8]
0x18001a4db  mov     ecx, [rcx+rax]; Value
0x18001a4de  call    cs:__imp__itow
0x18001a4e4  lea     r8, [rbp+57h+Buffer]
0x18001a4e8  mov     rdx, r14
0x18001a4eb  mov     rcx, [rsi]; Src
0x18001a4ee  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a4f3  mov     rax, [rsi+18h]
0x18001a4f7  mov     r8, [rax+8]
0x18001a4fb  mov     r8, [r8+0A8h]
0x18001a502  mov     rdx, r15
0x18001a505  mov     rcx, [rsi]; Src
0x18001a508  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a50d  nop
0x18001a50e  cmp     [rbp+57h+var_90], 8
0x18001a513  jb      short loc_18001A582
0x18001a515  mov     rcx, [rbp+57h+var_A8]
0x18001a519  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a51f  jmp     short loc_18001A582
0x18001a521  lea     rbx, aBackgroundBlue; "background = \"blue\" "
0x18001a528  mov     r8, rbx
0x18001a52b  lea     rdx, aButtoncontrolb_1; "%buttoncontrolbackgroundmouse"
0x18001a532  mov     rcx, [rsi]; Src
0x18001a535  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a53a  mov     r8, rbx
0x18001a53d  lea     rdx, aButtoncontrolb_3; "%buttoncontrolbackgroundkey"
0x18001a544  mov     rcx, [rsi]; Src
0x18001a547  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a54c  mov     r8, rbx
0x18001a54f  lea     rdx, aButtoncontrolb; "%buttoncontrolbackgroundboth"
0x18001a556  mov     rcx, [rsi]; Src
0x18001a559  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a55e  mov     r8, rbx
0x18001a561  lea     rdx, aButtoncontrolb_0; "%buttoncontrolbackgroundpress"
0x18001a568  mov     rcx, [rsi]; Src
0x18001a56b  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a570  mov     r8, rbx
0x18001a573  lea     rdx, aButtoncontrolb_2; "%buttoncontrolbackgroundrest"
0x18001a57a  mov     rcx, [rsi]; Src
0x18001a57d  call    ?DuiStringFindAndReplace@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAG1@Z; DuiStringFindAndReplace(std::wstring *,ushort *,ushort *)
0x18001a582  xor     ecx, ecx; nIndex
0x18001a584  call    cs:__imp_GetSystemMetrics
  ... truncated ...
```
