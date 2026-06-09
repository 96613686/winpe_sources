# CImmersiveIconicBitmapRegistry::BitmapReceived(CWindowData *,ulong,uint,uint,void *,unsigned __int64)

- ea: `0x1800b96cc`
- end: `0x1800b98a9`
- name: `?BitmapReceived@CImmersiveIconicBitmapRegistry@@QEAAJPEAVCWindowData@@KIIPEAX_K@Z`
- size: `477`
- prototype: `int(CImmersiveIconicBitmapRegistry *__hidden this, struct CWindowData *, unsigned int, unsigned int, unsigned int, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007867c`

## callees

- `0x180005948`
- `0x18001ce00`
- `0x18001f43c`
- `0x18004067c`
- `0x180089e80`
- `0x1800b96cc`
- `0x1800b9df4`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x1800b9700`
- `USER32!GetWindowThreadProcessId` at `0x1800b9746`
- `USER32!GetWindowThreadProcessId` at `0x1800b9700`
- `USER32!GetWindowThreadProcessId` at `0x1800b9746`

## pseudocode

```c
__int64 __fastcall CImmersiveIconicBitmapRegistry::BitmapReceived(
        CImmersiveIconicBitmapRegistry *this,
        struct CWindowData *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        int *a6,
        unsigned __int64 a7)
{
  __int64 v8; // r14
  CBaseObject *v10; // rdi
  HWND v12; // rcx
  unsigned __int64 v13; // rcx
  bool v14; // bl
  HWND ShellWindowForDesktop; // rax
  unsigned __int64 v16; // rax
  int *v17; // rdi
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // r8d
  int v21; // ecx
  int v22; // edx
  CBaseObject *v23; // r8
  DWORD dwProcessId; // [rsp+30h] [rbp-38h] BYREF
  CBaseObject *v26; // [rsp+38h] [rbp-30h] BYREF
  DWORD v27; // [rsp+78h] [rbp+10h] BYREF

  v8 = a4;
  v10 = 0;
  v26 = 0;
  v12 = (HWND)*((_QWORD *)a2 + 5);
  v27 = 0;
  if ( GetWindowThreadProcessId(v12, &v27) && a3 == v27 )
  {
    v14 = 1;
  }
  else
  {
    v14 = 0;
    ShellWindowForDesktop = CWindowList::GetShellWindowForDesktop(
                              *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                              *((_QWORD *)a2 + 17));
    if ( ShellWindowForDesktop )
    {
      dwProcessId = 0;
      GetWindowThreadProcessId(ShellWindowForDesktop, &dwProcessId);
      v14 = dwProcessId == a3;
    }
  }
  if ( (*((_BYTE *)a2 + 738) & 2) != 0
    && (v13 = a5 * v8, v13 <= 0xFFFFFFFF)
    && (v16 = 4LL * (unsigned int)v13, v16 <= 0xFFFFFFFF)
    && a7 >= (unsigned int)v16
    && v14 )
  {
    v17 = a6;
    v18 = CBitmapSource::Create(v8, a5, v8, a5, a6, &v26);
    v19 = v18;
    if ( v18 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, (const int *const)"W", 1u, v18, 0x171u, 0);
      v10 = v26;
    }
    else
    {
      v20 = *v17;
      v21 = *v17;
      v10 = v26;
      v22 = v20 & 0xFF00 | ((unsigned __int8)v20 << 16) | BYTE2(v21);
      v23 = v26;
      *((_DWORD *)a2 + 50) = v22;
      CImmersiveIconicBitmapRegistry::_AcceptBitmap(this, a2, v23);
    }
  }
  else
  {
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0qp_EtwEventWriteTransfer(v13, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
    v19 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, (const int *const)"W", 1u, -2147024809, 0x16Du, 0);
  }
  if ( v10 )
    CBaseObject::Release(v10);
  return v19;
}

```

## disassembly

```asm
0x1800b96cc  mov     rax, rsp
0x1800b96cf  mov     [rax+8], rbx
0x1800b96d3  mov     [rax+18h], rbp
0x1800b96d7  push    rsi
0x1800b96d8  push    rdi
0x1800b96d9  push    r13
0x1800b96db  push    r14
0x1800b96dd  push    r15
0x1800b96df  sub     rsp, 40h
0x1800b96e3  mov     rsi, rdx
0x1800b96e6  mov     r14d, r9d
0x1800b96e9  mov     r15, rcx
0x1800b96ec  lea     rdx, [rax+10h]; lpdwProcessId
0x1800b96f0  xor     edi, edi
0x1800b96f2  mov     ebp, r8d
0x1800b96f5  mov     [rax-30h], rdi
0x1800b96f9  mov     rcx, [rsi+28h]; hWnd
0x1800b96fd  mov     [rax+10h], edi
0x1800b9700  call    cs:__imp_GetWindowThreadProcessId
0x1800b9706  lea     r13d, [rdi+1]
0x1800b970a  test    eax, eax
0x1800b970c  jz      short loc_1800B9719
0x1800b970e  cmp     ebp, [rsp+68h+arg_8]
0x1800b9712  jnz     short loc_1800B9719
0x1800b9714  mov     bl, r13b
0x1800b9717  jmp     short loc_1800B9757
0x1800b9719  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800b9720  xor     bl, bl
0x1800b9722  mov     rdx, [rsi+88h]; unsigned __int64
0x1800b9729  mov     rcx, [rcx+1A8h]; this
0x1800b9730  call    ?GetShellWindowForDesktop@CWindowList@@QEAAPEAUHWND__@@_K@Z; CWindowList::GetShellWindowForDesktop(unsigned __int64)
0x1800b9735  test    rax, rax
0x1800b9738  jz      short loc_1800B9757
0x1800b973a  lea     rdx, [rsp+68h+dwProcessId]; lpdwProcessId
0x1800b973f  mov     [rsp+68h+dwProcessId], edi
0x1800b9743  mov     rcx, rax; hWnd
0x1800b9746  call    cs:__imp_GetWindowThreadProcessId
0x1800b974c  cmp     [rsp+68h+dwProcessId], ebp
0x1800b9750  movzx   ebx, bl
0x1800b9753  cmovz   ebx, r13d
0x1800b9757  test    byte ptr [rsi+2E2h], 2
0x1800b975e  jz      loc_1800B983C
0x1800b9764  mov     edx, [rsp+68h+arg_20]; unsigned int
0x1800b976b  mov     rcx, r14
0x1800b976e  imul    rcx, rdx
0x1800b9772  mov     r8d, 0FFFFFFFFh
0x1800b9778  cmp     rcx, r8
0x1800b977b  ja      loc_1800B983C
0x1800b9781  mov     eax, ecx
0x1800b9783  shl     rax, 2
0x1800b9787  cmp     rax, r8
0x1800b978a  ja      loc_1800B983C
0x1800b9790  mov     eax, eax
0x1800b9792  cmp     [rsp+68h+arg_30], rax
0x1800b979a  jb      loc_1800B983C
0x1800b97a0  test    bl, bl
0x1800b97a2  jz      loc_1800B983C
0x1800b97a8  mov     rdi, [rsp+68h+arg_28]
0x1800b97b0  lea     rax, [rsp+68h+var_30]
0x1800b97b5  mov     [rsp+68h+var_40], rax; struct CBitmapSource **
0x1800b97ba  mov     r9d, edx; unsigned int
0x1800b97bd  mov     r8d, r14d; unsigned int
0x1800b97c0  mov     [rsp+68h+var_48], rdi; void *
0x1800b97c5  mov     ecx, r14d; unsigned int
0x1800b97c8  call    ?Create@CBitmapSource@@SAJIIIIPEBXPEAPEAV1@@Z; CBitmapSource::Create(uint,uint,uint,uint,void const *,CBitmapSource * *)
0x1800b97cd  mov     ebx, eax
0x1800b97cf  test    eax, eax
0x1800b97d1  js      short loc_1800B980D
0x1800b97d3  mov     r8d, [rdi]
0x1800b97d6  mov     ecx, r8d
0x1800b97d9  mov     rdi, [rsp+68h+var_30]
0x1800b97de  shr     ecx, 10h
0x1800b97e1  movzx   edx, cl
0x1800b97e4  movzx   ecx, r8b
0x1800b97e8  and     r8d, 0FF00h
0x1800b97ef  shl     ecx, 10h
0x1800b97f2  or      edx, ecx
0x1800b97f4  mov     rcx, r15; this
0x1800b97f7  or      edx, r8d
0x1800b97fa  mov     r8, rdi; struct CBitmapSource *
0x1800b97fd  mov     [rsi+0C8h], edx
0x1800b9803  mov     rdx, rsi; struct CWindowData *
0x1800b9806  call    ?_AcceptBitmap@CImmersiveIconicBitmapRegistry@@AEAAXPEAVCWindowData@@PEAVCBitmapSource@@@Z; CImmersiveIconicBitmapRegistry::_AcceptBitmap(CWindowData *,CBitmapSource *)
0x1800b980b  jmp     short loc_1800B9881
0x1800b980d  mov     [rsp+68h+var_40], 0; void *
0x1800b9816  lea     rdx, aW_0; "W"
0x1800b981d  mov     r9d, eax; int
0x1800b9820  mov     dword ptr [rsp+68h+var_48], 171h; unsigned int
0x1800b9828  mov     r8d, r13d; unsigned int
0x1800b982b  mov     ecx, 14h; unsigned int
0x1800b9830  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800b9835  mov     rdi, [rsp+68h+var_30]
0x1800b983a  jmp     short loc_1800B9881
0x1800b983c  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, r13b
0x1800b9843  jz      short loc_1800B9858
0x1800b9845  mov     r9, [rsi+28h]
0x1800b9849  lea     rdx, UdwmManageIconicThumbnail_Info
0x1800b9850  mov     r8d, r13d
0x1800b9853  call    McTemplateU0qp_EtwEventWriteTransfer
0x1800b9858  mov     ebx, 80070057h
0x1800b985d  mov     [rsp+68h+var_40], rdi; void *
0x1800b9862  mov     r9d, ebx; int
0x1800b9865  mov     dword ptr [rsp+68h+var_48], 16Dh; unsigned int
0x1800b986d  mov     r8d, r13d; unsigned int
0x1800b9870  lea     rdx, aW_0; "W"
0x1800b9877  mov     ecx, 14h; unsigned int
0x1800b987c  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800b9881  test    rdi, rdi
0x1800b9884  jz      short loc_1800B988E
0x1800b9886  mov     rcx, rdi; this
0x1800b9889  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x1800b988e  lea     r11, [rsp+68h+var_28]
0x1800b9893  mov     eax, ebx
0x1800b9895  mov     rbx, [r11+30h]
0x1800b9899  mov     rbp, [r11+40h]
0x1800b989d  mov     rsp, r11
0x1800b98a0  pop     r15
0x1800b98a2  pop     r14
0x1800b98a4  pop     r13
0x1800b98a6  pop     rdi
0x1800b98a7  pop     rsi
0x1800b98a8  retn
```
