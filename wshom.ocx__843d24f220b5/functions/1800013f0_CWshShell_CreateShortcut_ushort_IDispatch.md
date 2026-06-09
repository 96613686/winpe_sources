# CWshShell::CreateShortcut(ushort *,IDispatch * *)

- ea: `0x1800013f0`
- end: `0x18000164c`
- name: `?CreateShortcut@CWshShell@@UEAAJPEAGPEAPEAUIDispatch@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CWshShell *this, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800013f0`
- `0x180005d20`
- `0x1800060e4`
- `0x180011010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000144b`
- `msvcrt!_wcsicmp` at `0x180001562`
- `msvcrt!_wcsicmp` at `0x18000144b`
- `msvcrt!_wcsicmp` at `0x180001562`
- `msvcrt!wcsrchr` at `0x18000142e`
- `msvcrt!wcsrchr` at `0x18000142e`

## string_xrefs

- `0x18000162f`: `WshShell.CreateShortcut`

## pseudocode

```c
__int64 __fastcall CWshShell::CreateShortcut(CWshShell *this, unsigned __int16 *a2, struct IDispatch **a3)
{
  wchar_t *v5; // rax
  const wchar_t *v6; // rbx
  struct IDispatch *v7; // rax
  struct IDispatch *v8; // rbx
  struct IDispatch *v9; // r14
  int v10; // esi
  struct IDispatch *v11; // rcx
  struct IDispatch v12; // rax
  struct IDispatch *v14; // rax

  if ( a3 )
  {
    *a3 = 0;
    if ( a2 )
    {
      v5 = wcsrchr(a2, 0x2Eu);
      if ( v5 )
      {
        v6 = v5 + 1;
        if ( !_wcsicmp(v5 + 1, L"LNK") )
        {
          v7 = (struct IDispatch *)operator new(0x60u);
          v8 = v7;
          if ( v7 )
          {
            v9 = 0;
            v7[1].lpVtbl = (struct IDispatchVtbl *)&CUnknown::`vftable';
            v7[4].lpVtbl = (struct IDispatchVtbl *)&CUnknown::InnerUnknown::`vftable';
            LODWORD(v7[5].lpVtbl) = 1;
            v7[2].lpVtbl = (struct IDispatchVtbl *)&v7[4];
            v7[3].lpVtbl = (struct IDispatchVtbl *)v7;
            _InterlockedIncrement(&Global::g_cObjects);
            LOBYTE(v7[7].lpVtbl) = 0;
            v7[6].lpVtbl = (struct IDispatchVtbl *)&TaUser_DescCWshShortcut;
            v7[9].lpVtbl = 0;
            v7->lpVtbl = (struct IDispatchVtbl *)&CWshShortcut::`vftable'{for `IWshShortcut'};
            v7[10].lpVtbl = 0;
            v7[1].lpVtbl = (struct IDispatchVtbl *)&CWshShortcut::`vftable'{for `CDispatch'};
            v7[8].lpVtbl = (struct IDispatchVtbl *)&CWshShortcut::`vftable'{for `IProvideClassInfo'};
            v7[11].lpVtbl = 0;
            v10 = ((__int64 (__fastcall *)(struct IDispatch *, unsigned __int16 *))CWshShortcut::Load)(v7, a2);
            if ( v10 < 0 )
            {
LABEL_9:
              ((void (__fastcall *)(struct IDispatch *))v8->lpVtbl->Release)(v8);
LABEL_10:
              if ( !v9 )
                return (unsigned int)v10;
LABEL_18:
              ((void (__fastcall *)(struct IDispatch *))v9->lpVtbl->Release)(v9);
              return (unsigned int)v10;
            }
            *a3 = v8;
            v11 = v8;
            v12.lpVtbl = v8->lpVtbl;
LABEL_8:
            ((void (__fastcall *)(struct IDispatch *))v12.lpVtbl->AddRef)(v11);
            v10 = 0;
            if ( !v8 )
              goto LABEL_10;
            goto LABEL_9;
          }
          return (unsigned int)-2147024882;
        }
        if ( !_wcsicmp(v6, L"URL") )
        {
          v14 = (struct IDispatch *)operator new(0x60u);
          v9 = v14;
          if ( v14 )
          {
            v14[1].lpVtbl = (struct IDispatchVtbl *)&CUnknown::`vftable';
            v14[4].lpVtbl = (struct IDispatchVtbl *)&CUnknown::InnerUnknown::`vftable';
            LODWORD(v14[5].lpVtbl) = 1;
            v14[2].lpVtbl = (struct IDispatchVtbl *)&v14[4];
            v14[3].lpVtbl = (struct IDispatchVtbl *)v14;
            _InterlockedIncrement(&Global::g_cObjects);
            LOBYTE(v14[7].lpVtbl) = 0;
            v14[6].lpVtbl = (struct IDispatchVtbl *)&TaUser_DescCWshURLShortcut;
            v14[9].lpVtbl = 0;
            v14->lpVtbl = (struct IDispatchVtbl *)&CWshURLShortcut::`vftable'{for `IWshURLShortcut'};
            v14[10].lpVtbl = 0;
            v14[1].lpVtbl = (struct IDispatchVtbl *)&CWshURLShortcut::`vftable'{for `CDispatch'};
            v14[8].lpVtbl = (struct IDispatchVtbl *)&CWshURLShortcut::`vftable'{for `IProvideClassInfo'};
            v14[11].lpVtbl = 0;
            v10 = ((__int64 (__fastcall *)(struct IDispatch *, unsigned __int16 *))CWshURLShortcut::Load)(v14, a2);
            if ( v10 < 0 )
              goto LABEL_18;
            *a3 = v9;
            v8 = 0;
            v12.lpVtbl = v9->lpVtbl;
            v11 = v9;
            goto LABEL_8;
          }
          return (unsigned int)-2147024882;
        }
      }
    }
    Signal_Exception(&IID_IWshShell, L"WshShell.CreateShortcut", 0x1004u);
    return (unsigned int)-2147352567;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800013f0  mov     [rsp+arg_18], rsi
0x1800013f5  push    rdi
0x1800013f6  sub     rsp, 20h
0x1800013fa  mov     rdi, r8
0x1800013fd  mov     rsi, rdx
0x180001400  test    r8, r8
0x180001403  jz      loc_180001548
0x180001409  mov     [rsp+28h+arg_0], rbx
0x18000140e  mov     [rsp+28h+arg_8], rbp
0x180001413  xor     ebp, ebp
0x180001415  mov     [rsp+28h+arg_10], r14
0x18000141a  mov     [r8], rbp
0x18000141d  test    rdx, rdx
0x180001420  jz      loc_180001629
0x180001426  mov     edx, 2Eh ; '.'; Ch
0x18000142b  mov     rcx, rsi; Str
0x18000142e  call    cs:__imp_wcsrchr
0x180001434  test    rax, rax
0x180001437  jz      loc_180001629
0x18000143d  lea     rbx, [rax+2]
0x180001441  mov     rcx, rbx; String1
0x180001444  lea     rdx, aLnk; "LNK"
0x18000144b  call    cs:__imp__wcsicmp
0x180001451  test    eax, eax
0x180001453  jnz     loc_180001558
0x180001459  mov     ecx, 60h ; '`'; Size
0x18000145e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001463  mov     rbx, rax
0x180001466  test    rax, rax
0x180001469  jz      loc_180001541
0x18000146f  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180001476  mov     r14d, ebp
0x180001479  mov     [rbx+8], rax
0x18000147d  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x180001484  lea     rax, [rbx+20h]
0x180001488  mov     [rax], rcx
0x18000148b  mov     dword ptr [rax+8], 1
0x180001492  mov     [rbx+10h], rax
0x180001496  mov     [rbx+18h], rbx
0x18000149a  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x1800014a1  mov     [rbx+38h], bpl
0x1800014a5  lea     rax, ?TaUser_DescCWshShortcut@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCWshShortcut
0x1800014ac  mov     [rbx+30h], rax
0x1800014b0  mov     rdx, rsi
0x1800014b3  lea     rax, ??_7CWshShortcut@@6BIWshShortcut@@@; const CWshShortcut::`vftable'{for `IWshShortcut'}
0x1800014ba  mov     [rbx+48h], rbp
0x1800014be  mov     [rbx], rax
0x1800014c1  mov     rcx, rbx
0x1800014c4  lea     rax, ??_7CWshShortcut@@6BCDispatch@@@; const CWshShortcut::`vftable'{for `CDispatch'}
0x1800014cb  mov     [rbx+50h], rbp
0x1800014cf  mov     [rbx+8], rax
0x1800014d3  lea     rax, ??_7CWshShortcut@@6BIProvideClassInfo@@@; const CWshShortcut::`vftable'{for `IProvideClassInfo'}
0x1800014da  mov     [rbx+40h], rax
0x1800014de  mov     [rbx+58h], rbp
0x1800014e2  mov     rax, cs:off_180012208
0x1800014e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ee  mov     esi, eax
0x1800014f0  test    eax, eax
0x1800014f2  js      short loc_18000150D
0x1800014f4  mov     [rdi], rbx
0x1800014f7  mov     rcx, rbx
0x1800014fa  mov     rax, [rbx]
0x1800014fd  mov     rax, [rax+8]
0x180001501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001506  mov     esi, ebp
0x180001508  test    rbx, rbx
0x18000150b  jz      short loc_18000151C
0x18000150d  mov     rax, [rbx]
0x180001510  mov     rcx, rbx
0x180001513  mov     rax, [rax+10h]
0x180001517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000151c  test    r14, r14
0x18000151f  jnz     loc_180001615
0x180001525  mov     r14, [rsp+28h+arg_10]
0x18000152a  mov     eax, esi
0x18000152c  mov     rbp, [rsp+28h+arg_8]
0x180001531  mov     rbx, [rsp+28h+arg_0]
0x180001536  mov     rsi, [rsp+28h+arg_18]
0x18000153b  add     rsp, 20h
0x18000153f  pop     rdi
0x180001540  retn
0x180001541  mov     esi, 8007000Eh
0x180001546  jmp     short loc_180001525
0x180001548  mov     rsi, [rsp+28h+arg_18]
0x18000154d  mov     eax, 80004003h
0x180001552  add     rsp, 20h
0x180001556  pop     rdi
0x180001557  retn
0x180001558  lea     rdx, aUrl; "URL"
0x18000155f  mov     rcx, rbx; String1
0x180001562  call    cs:__imp__wcsicmp
0x180001568  test    eax, eax
0x18000156a  jnz     loc_180001629
0x180001570  mov     ecx, 60h ; '`'; Size
0x180001575  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000157a  mov     r14, rax
0x18000157d  test    rax, rax
0x180001580  jz      short loc_180001541
0x180001582  lea     rax, ??_7CUnknown@@6B@; const CUnknown::`vftable'
0x180001589  mov     [r14+8], rax
0x18000158d  lea     rcx, ??_7InnerUnknown@CUnknown@@6B@; const CUnknown::InnerUnknown::`vftable'
0x180001594  lea     rax, [r14+20h]
0x180001598  mov     [rax], rcx
0x18000159b  mov     dword ptr [rax+8], 1
0x1800015a2  mov     [r14+10h], rax
0x1800015a6  mov     [r14+18h], r14
0x1800015aa  lock inc cs:?g_cObjects@Global@@2JA; long Global::g_cObjects
0x1800015b1  mov     [r14+38h], bpl
0x1800015b5  lea     rax, ?TaUser_DescCWshURLShortcut@@3UTaDescDispatch@@A; TaDescDispatch TaUser_DescCWshURLShortcut
0x1800015bc  mov     [r14+30h], rax
0x1800015c0  mov     rdx, rsi
0x1800015c3  lea     rax, ??_7CWshURLShortcut@@6BIWshURLShortcut@@@; const CWshURLShortcut::`vftable'{for `IWshURLShortcut'}
0x1800015ca  mov     [r14+48h], rbp
0x1800015ce  mov     [r14], rax
0x1800015d1  mov     rcx, r14
0x1800015d4  lea     rax, ??_7CWshURLShortcut@@6BCDispatch@@@; const CWshURLShortcut::`vftable'{for `CDispatch'}
0x1800015db  mov     [r14+50h], rbp
0x1800015df  mov     [r14+8], rax
0x1800015e3  lea     rax, ??_7CWshURLShortcut@@6BIProvideClassInfo@@@; const CWshURLShortcut::`vftable'{for `IProvideClassInfo'}
0x1800015ea  mov     [r14+40h], rax
0x1800015ee  mov     [r14+58h], rbp
0x1800015f2  mov     rax, cs:off_180012A58
0x1800015f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015fe  mov     esi, eax
0x180001600  test    eax, eax
0x180001602  js      short loc_180001615
0x180001604  mov     [rdi], r14
0x180001607  mov     rbx, rbp
0x18000160a  mov     rax, [r14]
0x18000160d  mov     rcx, r14
0x180001610  jmp     loc_1800014FD
0x180001615  mov     rax, [r14]
0x180001618  mov     rcx, r14
0x18000161b  mov     rax, [rax+10h]
0x18000161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001624  jmp     loc_180001525
0x180001629  mov     r8d, 1004h; unsigned int
0x18000162f  lea     rdx, aWshshellCreate; "WshShell.CreateShortcut"
0x180001636  lea     rcx, IID_IWshShell; struct _GUID *
0x18000163d  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x180001642  mov     esi, 80020009h
0x180001647  jmp     loc_180001525
```
