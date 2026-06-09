# CContactManager::LoadPenResources(void)

- ea: `0x1800acdc4`
- end: `0x1800aceef`
- name: `?LoadPenResources@CContactManager@@AEAAXXZ`
- size: `299`
- prototype: `void __fastcall(CContactManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001430c`

## callees

- `0x1800acd20`
- `0x1800acdc4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800acdf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800acdf7`
- `COMCTL32!InitCommonControlsEx` at `0x1800acde8`
- `COMCTL32!InitCommonControlsEx` at `0x1800acde8`

## pseudocode

```c
void __fastcall CContactManager::LoadPenResources(CContactManager *this)
{
  HMODULE ModuleHandleW; // rax
  CContactManager *v3; // rcx
  HINSTANCE v4; // rdi
  unsigned __int16 *v5; // rax
  CContactManager *v6; // rcx
  unsigned __int16 *v7; // rax
  CContactManager *v8; // rcx
  unsigned __int16 *v9; // rax
  CContactManager *v10; // rcx
  unsigned __int16 *v11; // rax
  CContactManager *v12; // rcx
  unsigned __int16 *v13; // rax
  CContactManager *v14; // rcx
  unsigned __int16 *v15; // rax
  int v16; // [rsp+30h] [rbp+10h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+38h] [rbp+18h] BYREF

  picce.dwSize = 8;
  picce.dwICC = 8;
  InitCommonControlsEx(&picce);
  *((_DWORD *)this + 12) = 0;
  ModuleHandleW = GetModuleHandleW(0);
  v4 = ModuleHandleW;
  if ( ModuleHandleW )
  {
    *((_DWORD *)this + 12) = 1;
    v16 = 0;
    v5 = CContactManager::LoadFeedbackString(v3, ModuleHandleW, 1501, &v16);
    *(_QWORD *)this = v5;
    if ( v5 )
      *((_DWORD *)this + 12) += v16;
    v7 = CContactManager::LoadFeedbackString(v6, v4, 1502, &v16);
    *((_QWORD *)this + 2) = v7;
    if ( v7 )
      *((_DWORD *)this + 12) += v16;
    v9 = CContactManager::LoadFeedbackString(v8, v4, 1503, &v16);
    *((_QWORD *)this + 1) = v9;
    if ( v9 )
      *((_DWORD *)this + 12) += v16;
    v11 = CContactManager::LoadFeedbackString(v10, v4, 1504, &v16);
    *((_QWORD *)this + 3) = v11;
    if ( v11 )
      *((_DWORD *)this + 12) += v16;
    v13 = CContactManager::LoadFeedbackString(v12, v4, 1505, &v16);
    *((_QWORD *)this + 4) = v13;
    if ( v13 )
      *((_DWORD *)this + 12) += v16;
    v15 = CContactManager::LoadFeedbackString(v14, v4, 1500, &v16);
    *((_QWORD *)this + 5) = v15;
    if ( v15 )
      *((_DWORD *)this + 12) += 4 * v16;
  }
}

```

## disassembly

```asm
0x1800acdc4  mov     [rsp-8+arg_10], rbx
0x1800acdc9  mov     [rsp-8+arg_18], rdi
0x1800acdce  push    rbp
0x1800acdcf  mov     rbp, rsp
0x1800acdd2  sub     rsp, 20h
0x1800acdd6  mov     eax, 8
0x1800acddb  mov     rbx, rcx
0x1800acdde  lea     rcx, [rbp+picce]; picce
0x1800acde2  mov     [rbp+picce.dwSize], eax
0x1800acde5  mov     [rbp+picce.dwICC], eax
0x1800acde8  call    cs:__imp_InitCommonControlsEx
0x1800acdee  xor     ecx, ecx; lpModuleName
0x1800acdf0  mov     dword ptr [rbx+30h], 0
0x1800acdf7  call    cs:__imp_GetModuleHandleW
0x1800acdfd  mov     rdi, rax
0x1800ace00  test    rax, rax
0x1800ace03  jz      loc_1800ACEDF
0x1800ace09  lea     r9, [rbp+arg_0]; int *
0x1800ace0d  mov     dword ptr [rbx+30h], 1
0x1800ace14  mov     r8d, 5DDh; int
0x1800ace1a  mov     [rbp+arg_0], 0
0x1800ace21  mov     rdx, rax; HINSTANCE
0x1800ace24  call    ?LoadFeedbackString@CContactManager@@IEAAPEAGPEAUHINSTANCE__@@HPEAH@Z; CContactManager::LoadFeedbackString(HINSTANCE__ *,int,int *)
0x1800ace29  mov     [rbx], rax
0x1800ace2c  test    rax, rax
0x1800ace2f  jz      short loc_1800ACE37
0x1800ace31  mov     eax, [rbp+arg_0]
0x1800ace34  add     [rbx+30h], eax
0x1800ace37  lea     r9, [rbp+arg_0]; int *
0x1800ace3b  mov     r8d, 5DEh; int
0x1800ace41  mov     rdx, rdi; HINSTANCE
0x1800ace44  call    ?LoadFeedbackString@CContactManager@@IEAAPEAGPEAUHINSTANCE__@@HPEAH@Z; CContactManager::LoadFeedbackString(HINSTANCE__ *,int,int *)
0x1800ace49  mov     [rbx+10h], rax
0x1800ace4d  test    rax, rax
0x1800ace50  jz      short loc_1800ACE58
0x1800ace52  mov     eax, [rbp+arg_0]
0x1800ace55  add     [rbx+30h], eax
0x1800ace58  lea     r9, [rbp+arg_0]; int *
0x1800ace5c  mov     r8d, 5DFh; int
0x1800ace62  mov     rdx, rdi; HINSTANCE
0x1800ace65  call    ?LoadFeedbackString@CContactManager@@IEAAPEAGPEAUHINSTANCE__@@HPEAH@Z; CContactManager::LoadFeedbackString(HINSTANCE__ *,int,int *)
0x1800ace6a  mov     [rbx+8], rax
0x1800ace6e  test    rax, rax
0x1800ace71  jz      short loc_1800ACE79
0x1800ace73  mov     eax, [rbp+arg_0]
0x1800ace76  add     [rbx+30h], eax
0x1800ace79  lea     r9, [rbp+arg_0]; int *
0x1800ace7d  mov     r8d, 5E0h; int
0x1800ace83  mov     rdx, rdi; HINSTANCE
0x1800ace86  call    ?LoadFeedbackString@CContactManager@@IEAAPEAGPEAUHINSTANCE__@@HPEAH@Z; CContactManager::LoadFeedbackString(HINSTANCE__ *,int,int *)
0x1800ace8b  mov     [rbx+18h], rax
0x1800ace8f  test    rax, rax
0x1800ace92  jz      short loc_1800ACE9A
0x1800ace94  mov     eax, [rbp+arg_0]
0x1800ace97  add     [rbx+30h], eax
0x1800ace9a  lea     r9, [rbp+arg_0]; int *
0x1800ace9e  mov     r8d, 5E1h; int
0x1800acea4  mov     rdx, rdi; HINSTANCE
0x1800acea7  call    ?LoadFeedbackString@CContactManager@@IEAAPEAGPEAUHINSTANCE__@@HPEAH@Z; CContactManager::LoadFeedbackString(HINSTANCE__ *,int,int *)
0x1800aceac  mov     [rbx+20h], rax
0x1800aceb0  test    rax, rax
0x1800aceb3  jz      short loc_1800ACEBB
0x1800aceb5  mov     eax, [rbp+arg_0]
0x1800aceb8  add     [rbx+30h], eax
0x1800acebb  lea     r9, [rbp+arg_0]; int *
0x1800acebf  mov     r8d, 5DCh; int
0x1800acec5  mov     rdx, rdi; HINSTANCE
0x1800acec8  call    ?LoadFeedbackString@CContactManager@@IEAAPEAGPEAUHINSTANCE__@@HPEAH@Z; CContactManager::LoadFeedbackString(HINSTANCE__ *,int,int *)
0x1800acecd  mov     [rbx+28h], rax
0x1800aced1  test    rax, rax
0x1800aced4  jz      short loc_1800ACEDF
0x1800aced6  mov     eax, [rbp+arg_0]
0x1800aced9  shl     eax, 2
0x1800acedc  add     [rbx+30h], eax
0x1800acedf  mov     rbx, [rsp+20h+arg_10]
0x1800acee4  mov     rdi, [rsp+20h+arg_18]
0x1800acee9  add     rsp, 20h
0x1800aceed  pop     rbp
0x1800aceee  retn
```
