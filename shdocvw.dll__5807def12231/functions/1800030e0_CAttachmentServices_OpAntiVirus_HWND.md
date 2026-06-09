# CAttachmentServices::_OpAntiVirus(HWND__ *)

- ea: `0x1800030e0`
- end: `0x1800032dc`
- name: `?_OpAntiVirus@CAttachmentServices@@AEAAXPEAUHWND__@@@Z`
- size: `508`
- prototype: `void __fastcall(CAttachmentServices *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000d110`
- `0x18001143c`

## callees

- `0x180002d10`
- `0x1800030e0`
- `0x1800033a0`
- `0x180004340`
- `0x180008320`
- `0x180029010`

## import_xrefs

- `SHELL32!__imp_SHEnumClassesOfCategories` at `0x1800031ce`
- `SHELL32!__imp_SHEnumClassesOfCategories` at `0x1800031ce`
- `SHELL32!__imp_SHWriteClassesOfCategories` at `0x1800031a4`
- `SHELL32!__imp_SHWriteClassesOfCategories` at `0x1800031a4`

## pseudocode

```c
void __fastcall CAttachmentServices::_OpAntiVirus(CAttachmentServices *this, HWND a2)
{
  bool v4; // zf
  int v5; // edi
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v8; // r11d
  char *v9; // rdx
  int v10; // [rsp+40h] [rbp-58h] BYREF
  __int64 v11; // [rsp+48h] [rbp-50h] BYREF
  __int128 v12; // [rsp+50h] [rbp-48h] BYREF
  GUID v13; // [rsp+60h] [rbp-38h] BYREF

  if ( !*((_QWORD *)this + 36) && !*((_DWORD *)this + 63) )
  {
    if ( *((_DWORD *)this + 62) == 1 )
    {
      *((_DWORD *)this + 63) = 2;
    }
    else
    {
      v4 = dword_1800389B8 == 0;
      *((_DWORD *)this + 63) = 1;
      v5 = *((_DWORD *)this + 75);
      v13 = CATID_MSOfficeAntiVirus;
      *((_DWORD *)this + 75) = 9;
      v11 = 0;
      if ( v4 )
      {
        SHWriteClassesOfCategories(1, &v13, 0, 0, 1, 0, 0);
        dword_1800389B8 = 1;
      }
      if ( (int)SHEnumClassesOfCategories(1, &v13, 0, 0, &v11) >= 0 )
      {
        v10 = 0;
        v12 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int128 *, int *))(*(_QWORD *)v11 + 24LL))(
                v11,
                1,
                &v12,
                &v10) )
        {
          do
          {
            v7 = _SHExtCoCreateInstanceAndScan(&v12, v6, a2, *((_QWORD *)this + 5), *((_QWORD *)this + 6));
            if ( (unsigned int)CAttachmentServices::ReportResult(this, v7, 1) )
              v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int128 *, int *))(*(_QWORD *)v11 + 24LL))(
                     v11,
                     1,
                     &v12,
                     &v10);
          }
          while ( !v8 );
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v9 = (char *)this + 16 * *((int *)this + 75);
      if ( *((_DWORD *)v9 + 27) == 1 )
      {
        if ( *((_DWORD *)v9 + 25) && *((_DWORD *)this + 75) != 1 && (unsigned int)CAttachmentServices::Continuable(this) )
          *((_DWORD *)v9 + 27) = 4;
        else
          *((_DWORD *)v9 + 27) = 0;
      }
      *((_DWORD *)this + 75) = v5;
    }
  }
}

```

## disassembly

```asm
0x1800030e0  push    rbx
0x1800030e2  push    rsi
0x1800030e3  sub     rsp, 88h
0x1800030ea  mov     rax, cs:__security_cookie
0x1800030f1  xor     rax, rsp
0x1800030f4  mov     [rsp+98h+var_28], rax
0x1800030f9  cmp     dword ptr [rcx+120h], 0
0x180003100  mov     rsi, rdx
0x180003103  mov     rbx, rcx
0x180003106  jnz     loc_1800032C5
0x18000310c  cmp     dword ptr [rcx+124h], 0
0x180003113  jnz     loc_1800032C5
0x180003119  cmp     dword ptr [rcx+0FCh], 0
0x180003120  jnz     loc_1800032C5
0x180003126  cmp     dword ptr [rcx+0F8h], 1
0x18000312d  jnz     short loc_18000313E
0x18000312f  mov     dword ptr [rcx+0FCh], 2
0x180003139  jmp     loc_1800032C5
0x18000313e  movups  xmm0, xmmword ptr cs:CATID_MSOfficeAntiVirus.Data1
0x180003145  mov     [rsp+98h+arg_10], rbp
0x18000314d  xor     ebp, ebp
0x18000314f  cmp     cs:dword_1800389B8, ebp
0x180003155  mov     dword ptr [rcx+0FCh], 1
0x18000315f  mov     [rsp+98h+var_18], rdi
0x180003167  mov     edi, [rcx+12Ch]
0x18000316d  movups  [rsp+98h+var_38], xmm0
0x180003172  mov     dword ptr [rcx+12Ch], 9
0x18000317c  mov     [rsp+98h+var_50], rbp
0x180003181  jnz     short loc_1800031B4
0x180003183  mov     [rsp+98h+var_68], rbp
0x180003188  lea     rdx, [rsp+98h+var_38]
0x18000318d  mov     [rsp+98h+var_70], ebp
0x180003191  xor     r9d, r9d
0x180003194  xor     r8d, r8d
0x180003197  mov     dword ptr [rsp+98h+var_78], 1
0x18000319f  mov     ecx, 1
0x1800031a4  call    cs:__imp_SHWriteClassesOfCategories
0x1800031aa  mov     cs:dword_1800389B8, 1
0x1800031b4  lea     rax, [rsp+98h+var_50]
0x1800031b9  xor     r9d, r9d
0x1800031bc  xor     r8d, r8d
0x1800031bf  mov     [rsp+98h+var_78], rax
0x1800031c4  lea     rdx, [rsp+98h+var_38]
0x1800031c9  mov     ecx, 1
0x1800031ce  call    cs:__imp_SHEnumClassesOfCategories
0x1800031d4  test    eax, eax
0x1800031d6  js      loc_180003276
0x1800031dc  mov     rcx, [rsp+98h+var_50]
0x1800031e1  lea     r9, [rsp+98h+var_58]
0x1800031e6  xorps   xmm0, xmm0
0x1800031e9  mov     [rsp+98h+var_58], ebp
0x1800031ed  movups  [rsp+98h+var_48], xmm0
0x1800031f2  lea     r8, [rsp+98h+var_48]
0x1800031f7  mov     edx, 1
0x1800031fc  mov     rax, [rcx]
0x1800031ff  mov     rax, [rax+18h]
0x180003203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003208  test    eax, eax
0x18000320a  jnz     short loc_180003265
0x18000320c  mov     rax, [rbx+30h]
0x180003210  lea     rcx, [rsp+98h+var_48]
0x180003215  mov     r9, [rbx+28h]
0x180003219  mov     r8, rsi
0x18000321c  mov     [rsp+98h+var_78], rax
0x180003221  call    ?_SHExtCoCreateInstanceAndScan@@YAJAEBU_GUID@@W4EXTCOCREATEFLAGS@@PEAUHWND__@@PEBG3@Z; _SHExtCoCreateInstanceAndScan(_GUID const &,EXTCOCREATEFLAGS,HWND__ *,ushort const *,ushort const *)
0x180003226  mov     r8d, 1
0x18000322c  mov     edx, eax
0x18000322e  mov     rcx, rbx
0x180003231  mov     r11d, eax
0x180003234  call    ?ReportResult@CAttachmentServices@@AEAAHJW4OP_RESULT@1@@Z; CAttachmentServices::ReportResult(long,CAttachmentServices::OP_RESULT)
0x180003239  test    eax, eax
0x18000323b  jz      short loc_180003260
0x18000323d  mov     rcx, [rsp+98h+var_50]
0x180003242  lea     r9, [rsp+98h+var_58]
0x180003247  lea     r8, [rsp+98h+var_48]
0x18000324c  mov     edx, 1
0x180003251  mov     rax, [rcx]
0x180003254  mov     rax, [rax+18h]
0x180003258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325d  mov     r11d, eax
0x180003260  test    r11d, r11d
0x180003263  jz      short loc_18000320C
0x180003265  mov     rcx, [rsp+98h+var_50]
0x18000326a  mov     rax, [rcx]
0x18000326d  mov     rax, [rax+10h]
0x180003271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003276  movsxd  rcx, dword ptr [rbx+12Ch]
0x18000327d  mov     rdx, rcx
0x180003280  shl     rdx, 4
0x180003284  add     rdx, rbx
0x180003287  cmp     dword ptr [rdx+6Ch], 1
0x18000328b  jnz     short loc_1800032AF
0x18000328d  cmp     [rdx+64h], ebp
0x180003290  jz      short loc_1800032AC
0x180003292  cmp     ecx, 1
0x180003295  jz      short loc_1800032AC
0x180003297  mov     rcx, rbx; this
0x18000329a  call    ?Continuable@CAttachmentServices@@AEAAHXZ; CAttachmentServices::Continuable(void)
0x18000329f  test    eax, eax
0x1800032a1  jz      short loc_1800032AC
0x1800032a3  mov     dword ptr [rdx+6Ch], 4
0x1800032aa  jmp     short loc_1800032AF
0x1800032ac  mov     [rdx+6Ch], ebp
0x1800032af  mov     rbp, [rsp+98h+arg_10]
0x1800032b7  mov     [rbx+12Ch], edi
0x1800032bd  mov     rdi, [rsp+98h+var_18]
0x1800032c5  mov     rcx, [rsp+98h+var_28]
0x1800032ca  xor     rcx, rsp; StackCookie
0x1800032cd  call    __security_check_cookie
0x1800032d2  add     rsp, 88h
0x1800032d9  pop     rsi
0x1800032da  pop     rbx
0x1800032db  retn
```
