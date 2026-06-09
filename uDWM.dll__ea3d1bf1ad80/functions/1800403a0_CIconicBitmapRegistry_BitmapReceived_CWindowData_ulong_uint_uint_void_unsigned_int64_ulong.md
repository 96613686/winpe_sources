# CIconicBitmapRegistry::BitmapReceived(CWindowData *,ulong,uint,uint,void *,unsigned __int64,ulong)

- ea: `0x1800403a0`
- end: `0x180040673`
- name: `?BitmapReceived@CIconicBitmapRegistry@@QEAAJPEAVCWindowData@@KIIPEAX_KK@Z`
- size: `723`
- prototype: `__int64 __fastcall(CIconicBitmapRegistry *this, struct CWindowData *, int, unsigned int, LONG nNumber, void *, unsigned __int64, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007867c`

## callees

- `0x180005948`
- `0x18001ce00`
- `0x18001f43c`
- `0x1800403a0`
- `0x18004067c`
- `0x1800420a8`
- `0x180042e9c`
- `0x1800430d0`
- `0x18006c1dc`
- `0x180089e80`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004054e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180040577`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18004054e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x180040577`
- `USER32!GetWindowThreadProcessId` at `0x1800403d9`
- `USER32!GetWindowThreadProcessId` at `0x18004041d`
- `USER32!GetWindowThreadProcessId` at `0x1800403d9`
- `USER32!GetWindowThreadProcessId` at `0x18004041d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIconicBitmapRegistry::BitmapReceived(
        CIconicBitmapRegistry *this,
        struct CWindowData *a2,
        int a3,
        unsigned int a4,
        LONG nNumber,
        void *a6,
        unsigned __int64 a7,
        char a8)
{
  __int64 v9; // r15
  CBaseObject *v11; // rsi
  HWND v13; // rcx
  unsigned __int64 v14; // rcx
  bool v15; // bl
  HWND ShellWindowForDesktop; // rax
  LONG v17; // r14d
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // ebx
  unsigned int v21; // r12d
  unsigned int v22; // r13d
  __int64 v23; // rcx
  LONG cx; // ebx
  LONG cy; // esi
  int v26; // eax
  char v27; // cl
  CBaseObject *v28; // r8
  CBaseObject *v30; // [rsp+30h] [rbp-10h] BYREF
  struct tagSIZE v32; // [rsp+88h] [rbp+48h] BYREF
  DWORD dwProcessId; // [rsp+98h] [rbp+58h] BYREF

  v9 = a4;
  v11 = 0;
  v30 = 0;
  v13 = (HWND)*((_QWORD *)a2 + 5);
  dwProcessId = 0;
  if ( GetWindowThreadProcessId(v13, &dwProcessId) && a3 == dwProcessId )
  {
    v15 = 1;
  }
  else
  {
    v15 = 0;
    ShellWindowForDesktop = CWindowList::GetShellWindowForDesktop(
                              *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                              *((_QWORD *)a2 + 17));
    if ( ShellWindowForDesktop )
    {
      v32.cx = 0;
      GetWindowThreadProcessId(ShellWindowForDesktop, (LPDWORD)&v32);
      v15 = v32.cx == a3;
    }
  }
  if ( (*((_BYTE *)a2 + 738) & 2) != 0
    && (v17 = nNumber, v14 = (unsigned int)nNumber * v9, v14 <= 0xFFFFFFFF)
    && (v18 = 4LL * (unsigned int)v14, v18 <= 0xFFFFFFFF)
    && a7 >= (unsigned int)v18
    && v15 )
  {
    if ( !CIconicBitmapRegistry::CanAcceptBitmap(this, a2) )
    {
      v20 = 0;
      if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
        McTemplateU0qp_EtwEventWriteTransfer(v19, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
      return v20;
    }
    v21 = v9;
    v22 = v17;
    if ( !IsWindowTab(a2) )
    {
      v32 = 0;
      if ( !(unsigned int)DwmGetIdealIconicThumbnailSize(1, &v32) )
      {
        if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
          McTemplateU0qp_EtwEventWriteTransfer(v23, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
        v20 = -2147467259;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F5948, 1u, -2147467259, 0x296u, 0);
        return v20;
      }
      cx = v32.cx;
      cy = v32.cy;
      if ( (int)v9 <= v32.cx || (int)v9 * v32.cy > v17 * v32.cx )
      {
        if ( v17 > v32.cy && (int)v9 * v32.cy > v17 * v32.cx )
        {
          v21 = MulDiv(v9, v32.cy, v17);
          v22 = cy;
        }
      }
      else
      {
        v22 = MulDiv(v17, v32.cx, v9);
        v21 = cx;
      }
    }
    v26 = CBitmapSource::Create(v9, v17, v21, v22, a6, &v30);
    v20 = v26;
    if ( v26 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F5948, 1u, v26, 0x2A5u, 0);
      v11 = v30;
    }
    else
    {
      v27 = a8;
      *((_BYTE *)a2 + 738) &= ~4u;
      v11 = v30;
      v28 = v30;
      *((_BYTE *)a2 + 738) |= 4 * (v27 & 1);
      CIconicBitmapRegistry::AcceptBitmap(this, a2, v28);
    }
  }
  else
  {
    if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      McTemplateU0qp_EtwEventWriteTransfer(v14, UdwmManageIconicThumbnail_Info, 1, *((_QWORD *)a2 + 5));
    v20 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1800F5948, 1u, -2147024809, 0x284u, 0);
  }
  if ( v11 )
    CBaseObject::Release(v11);
  return v20;
}

```

## disassembly

```asm
0x1800403a0  mov     [rsp-38h+arg_10], rbx
0x1800403a5  mov     [rsp-38h+arg_0], rcx
0x1800403aa  push    rbp
0x1800403ab  push    rsi
0x1800403ac  push    rdi
0x1800403ad  push    r12
0x1800403af  push    r13
0x1800403b1  push    r14
0x1800403b3  push    r15
0x1800403b5  mov     rbp, rsp
0x1800403b8  sub     rsp, 40h
0x1800403bc  mov     rdi, rdx
0x1800403bf  mov     r15d, r9d
0x1800403c2  mov     r12, rcx
0x1800403c5  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x1800403c9  xor     esi, esi
0x1800403cb  mov     r14d, r8d
0x1800403ce  mov     [rbp+var_10], rsi
0x1800403d2  mov     rcx, [rdi+28h]; hWnd
0x1800403d6  mov     [rbp+dwProcessId], esi
0x1800403d9  call    cs:__imp_GetWindowThreadProcessId
0x1800403df  lea     r13d, [rsi+1]
0x1800403e3  test    eax, eax
0x1800403e5  jz      short loc_1800403F2
0x1800403e7  cmp     r14d, [rbp+dwProcessId]
0x1800403eb  jnz     short loc_1800403F2
0x1800403ed  mov     bl, r13b
0x1800403f0  jmp     short loc_18004042E
0x1800403f2  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x1800403f9  xor     bl, bl
0x1800403fb  mov     rdx, [rdi+88h]; unsigned __int64
0x180040402  mov     rcx, [rcx+1A8h]; this
0x180040409  call    ?GetShellWindowForDesktop@CWindowList@@QEAAPEAUHWND__@@_K@Z; CWindowList::GetShellWindowForDesktop(unsigned __int64)
0x18004040e  test    rax, rax
0x180040411  jz      short loc_18004042E
0x180040413  lea     rdx, [rbp+arg_8]; lpdwProcessId
0x180040417  mov     dword ptr [rbp+arg_8], esi
0x18004041a  mov     rcx, rax; hWnd
0x18004041d  call    cs:__imp_GetWindowThreadProcessId
0x180040423  cmp     dword ptr [rbp+arg_8], r14d
0x180040427  movzx   ebx, bl
0x18004042a  cmovz   ebx, r13d
0x18004042e  test    byte ptr [rdi+2E2h], 2
0x180040435  jz      loc_180040607
0x18004043b  mov     r14d, [rbp+nNumber]
0x18004043f  mov     rcx, r15
0x180040442  imul    rcx, r14
0x180040446  mov     edx, 0FFFFFFFFh
0x18004044b  cmp     rcx, rdx
0x18004044e  ja      loc_180040607
0x180040454  mov     eax, ecx
0x180040456  shl     rax, 2
0x18004045a  cmp     rax, rdx
0x18004045d  ja      loc_180040607
0x180040463  mov     eax, eax
0x180040465  cmp     [rbp+arg_30], rax
0x180040469  jb      loc_180040607
0x18004046f  test    bl, bl
0x180040471  jz      loc_180040607
0x180040477  mov     rdx, rdi; struct CWindowData *
0x18004047a  mov     rcx, r12; this
0x18004047d  call    ?CanAcceptBitmap@CIconicBitmapRegistry@@AEAA_NPEAVCWindowData@@@Z; CIconicBitmapRegistry::CanAcceptBitmap(CWindowData *)
0x180040482  test    al, al
0x180040484  jnz     short loc_1800404AD
0x180040486  xor     ebx, ebx
0x180040488  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, r13b
0x18004048f  jz      loc_180040659
0x180040495  mov     r9, [rdi+28h]
0x180040499  lea     rdx, UdwmManageIconicThumbnail_Info
0x1800404a0  mov     r8d, r13d
0x1800404a3  call    McTemplateU0qp_EtwEventWriteTransfer
0x1800404a8  jmp     loc_180040659
0x1800404ad  mov     rcx, rdi; struct CWindowData *
0x1800404b0  mov     r12d, r15d
0x1800404b3  mov     r13d, r14d
0x1800404b6  call    ?IsWindowTab@@YA_NPEAVCWindowData@@@Z; IsWindowTab(CWindowData *)
0x1800404bb  test    al, al
0x1800404bd  jnz     loc_180040583
0x1800404c3  mov     [rbp+arg_8], rsi
0x1800404c7  lea     rdx, [rbp+arg_8]; struct tagSIZE *
0x1800404cb  mov     esi, 1
0x1800404d0  mov     cl, sil; bool
0x1800404d3  call    ?DwmGetIdealIconicThumbnailSize@@YAH_NPEAUtagSIZE@@@Z; DwmGetIdealIconicThumbnailSize(bool,tagSIZE *)
0x1800404d8  test    eax, eax
0x1800404da  jnz     short loc_18004052A
0x1800404dc  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, sil
0x1800404e3  jz      short loc_1800404F8
0x1800404e5  mov     r9, [rdi+28h]
0x1800404e9  lea     rdx, UdwmManageIconicThumbnail_Info
0x1800404f0  mov     r8d, esi
0x1800404f3  call    McTemplateU0qp_EtwEventWriteTransfer
0x1800404f8  mov     ebx, 80004005h
0x1800404fd  mov     [rsp+40h+var_18], 0; void *
0x180040506  mov     r9d, ebx; int
0x180040509  mov     dword ptr [rsp+40h+var_20], 296h; unsigned int
0x180040511  mov     r8d, esi; unsigned int
0x180040514  lea     rdx, qword_1800F5948; int *
0x18004051b  mov     ecx, 14h; unsigned int
0x180040520  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180040525  jmp     loc_180040659
0x18004052a  mov     rbx, [rbp+arg_8]
0x18004052e  mov     esi, dword ptr [rbp+arg_8+4]
0x180040531  cmp     r15d, ebx
0x180040534  jle     short loc_18004055C
0x180040536  mov     ecx, esi
0x180040538  mov     eax, ebx
0x18004053a  imul    ecx, r15d
0x18004053e  imul    eax, r14d
0x180040542  cmp     ecx, eax
0x180040544  jg      short loc_18004055C
0x180040546  mov     r8d, r15d; nDenominator
0x180040549  mov     edx, ebx; nNumerator
0x18004054b  mov     ecx, r14d; nNumber
0x18004054e  call    cs:__imp_MulDiv
0x180040554  mov     r13d, eax
0x180040557  mov     r12d, ebx
0x18004055a  jmp     short loc_180040583
0x18004055c  cmp     r14d, esi
0x18004055f  jle     short loc_180040583
0x180040561  mov     eax, esi
0x180040563  imul    ebx, r14d
0x180040567  imul    eax, r15d
0x18004056b  cmp     eax, ebx
0x18004056d  jle     short loc_180040583
0x18004056f  mov     r8d, r14d; nDenominator
0x180040572  mov     edx, esi; nNumerator
0x180040574  mov     ecx, r15d; nNumber
0x180040577  call    cs:__imp_MulDiv
0x18004057d  mov     r12d, eax
0x180040580  mov     r13d, esi
0x180040583  mov     rcx, [rbp+arg_28]
0x180040587  lea     rax, [rbp+var_10]
0x18004058b  mov     [rsp+40h+var_18], rax; struct CBitmapSource **
0x180040590  mov     r9d, r13d; unsigned int
0x180040593  mov     [rsp+40h+var_20], rcx; void *
0x180040598  mov     r8d, r12d; unsigned int
0x18004059b  mov     ecx, r15d; unsigned int
0x18004059e  mov     edx, r14d; unsigned int
0x1800405a1  call    ?Create@CBitmapSource@@SAJIIIIPEBXPEAPEAV1@@Z; CBitmapSource::Create(uint,uint,uint,uint,void const *,CBitmapSource * *)
0x1800405a6  mov     ebx, eax
0x1800405a8  test    eax, eax
0x1800405aa  js      short loc_1800405D7
0x1800405ac  mov     cl, byte ptr [rbp+arg_38]
0x1800405af  mov     rdx, rdi; struct CWindowData *
0x1800405b2  and     byte ptr [rdi+2E2h], 0FBh
0x1800405b9  and     cl, 1
0x1800405bc  mov     rsi, [rbp+var_10]
0x1800405c0  shl     cl, 2
0x1800405c3  mov     r8, rsi; struct CBitmapSource *
0x1800405c6  or      [rdi+2E2h], cl
0x1800405cc  mov     rcx, [rbp+arg_0]; this
0x1800405d0  call    ?AcceptBitmap@CIconicBitmapRegistry@@AEAAXPEAVCWindowData@@PEAVCBitmapSource@@@Z; CIconicBitmapRegistry::AcceptBitmap(CWindowData *,CBitmapSource *)
0x1800405d5  jmp     short loc_18004064C
0x1800405d7  mov     r8d, 1; unsigned int
0x1800405dd  mov     [rsp+40h+var_18], 0; void *
0x1800405e6  mov     r9d, eax; int
0x1800405e9  mov     dword ptr [rsp+40h+var_20], 2A5h; unsigned int
0x1800405f1  lea     rdx, qword_1800F5948; int *
0x1800405f8  lea     ecx, [r8+13h]; unsigned int
0x1800405fc  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180040601  mov     rsi, [rbp+var_10]
0x180040605  jmp     short loc_18004064C
0x180040607  test    byte ptr cs:Microsoft_Windows_Dwm_UdwmEnableBits, r13b
0x18004060e  jz      short loc_180040623
0x180040610  mov     r9, [rdi+28h]
0x180040614  lea     rdx, UdwmManageIconicThumbnail_Info
0x18004061b  mov     r8d, r13d
0x18004061e  call    McTemplateU0qp_EtwEventWriteTransfer
0x180040623  mov     ebx, 80070057h
0x180040628  mov     [rsp+40h+var_18], rsi; void *
0x18004062d  mov     r9d, ebx; int
0x180040630  mov     dword ptr [rsp+40h+var_20], 284h; unsigned int
0x180040638  mov     r8d, r13d; unsigned int
0x18004063b  lea     rdx, qword_1800F5948; int *
0x180040642  mov     ecx, 14h; unsigned int
0x180040647  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18004064c  test    rsi, rsi
0x18004064f  jz      short loc_180040659
0x180040651  mov     rcx, rsi; this
0x180040654  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x180040659  mov     eax, ebx
0x18004065b  mov     rbx, [rsp+40h+arg_10]
0x180040663  add     rsp, 40h
0x180040667  pop     r15
0x180040669  pop     r14
0x18004066b  pop     r13
0x18004066d  pop     r12
0x18004066f  pop     rdi
0x180040670  pop     rsi
0x180040671  pop     rbp
0x180040672  retn
```
