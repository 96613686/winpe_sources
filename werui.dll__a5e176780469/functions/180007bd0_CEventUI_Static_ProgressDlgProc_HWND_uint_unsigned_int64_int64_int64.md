# CEventUI::Static_ProgressDlgProc(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x180007bd0`
- end: `0x180007c60`
- name: `?Static_ProgressDlgProc@CEventUI@@CAJPEAUHWND__@@I_K_J2@Z`
- size: `144`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006b10`
- `0x180006bdc`
- `0x180007bd0`

## import_xrefs

- `COMCTL32!__imp_RemoveWindowSubclass` at `0x180007c09`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x180007c09`

## pseudocode

```c
__int64 __fastcall CEventUI::Static_ProgressDlgProc(
        HWND hWnd,
        int a2,
        unsigned __int64 a3,
        __int64 a4,
        CEventUI *dwRefData)
{
  unsigned int v5; // ebx
  int v7; // edx
  int v8; // edx
  DWORD_PTR v10; // rcx
  int v11; // r8d

  v5 = 0;
  if ( !a2 )
  {
    v10 = (DWORD_PTR)dwRefData;
    v11 = 0;
    return (unsigned int)CEventUI::OnInitProgressDialog(v10, hWnd, v11);
  }
  v7 = a2 - 1;
  if ( !v7 )
  {
    v10 = (DWORD_PTR)dwRefData;
    if ( !*((_DWORD *)dwRefData + 235) )
      return v5;
    *((_DWORD *)dwRefData + 235) = 0;
    v11 = 1;
    return (unsigned int)CEventUI::OnInitProgressDialog(v10, hWnd, v11);
  }
  v8 = v7 - 1;
  if ( !v8 )
    return (unsigned int)CEventUI::OnCommandProgressDialog(dwRefData, a3);
  if ( v8 == 3 && *((_DWORD *)dwRefData + 233) )
  {
    RemoveWindowSubclass(hWnd, CEventUI::Static_ProgressDialogSubclassProc, 0);
    *((_DWORD *)dwRefData + 233) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180007bd0  mov     [rsp+arg_0], rbx
0x180007bd5  push    rdi
0x180007bd6  sub     rsp, 20h
0x180007bda  xor     ebx, ebx
0x180007bdc  mov     rax, rcx
0x180007bdf  test    edx, edx
0x180007be1  jz      short loc_180007C41
0x180007be3  sub     edx, 1
0x180007be6  jz      short loc_180007C26
0x180007be8  sub     edx, 1
0x180007beb  jz      short loc_180007C17
0x180007bed  cmp     edx, 3
0x180007bf0  jnz     short loc_180007C53
0x180007bf2  mov     rdi, [rsp+28h+dwRefData]
0x180007bf7  cmp     [rdi+3A4h], ebx
0x180007bfd  jz      short loc_180007C53
0x180007bff  xor     r8d, r8d; uIdSubclass
0x180007c02  lea     rdx, ?Static_ProgressDialogSubclassProc@CEventUI@@CA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x180007c09  call    cs:__imp_RemoveWindowSubclass
0x180007c0f  mov     [rdi+3A4h], ebx
0x180007c15  jmp     short loc_180007C53
0x180007c17  mov     rcx, [rsp+28h+dwRefData]; this
0x180007c1c  mov     rdx, r8; unsigned __int64
0x180007c1f  call    ?OnCommandProgressDialog@CEventUI@@AEAAJ_K@Z; CEventUI::OnCommandProgressDialog(unsigned __int64)
0x180007c24  jmp     short loc_180007C51
0x180007c26  mov     rcx, [rsp+28h+dwRefData]
0x180007c2b  cmp     [rcx+3ACh], ebx
0x180007c31  jz      short loc_180007C53
0x180007c33  mov     [rcx+3ACh], ebx
0x180007c39  mov     r8d, 1
0x180007c3f  jmp     short loc_180007C49
0x180007c41  mov     rcx, [rsp+28h+dwRefData]; dwRefData
0x180007c46  xor     r8d, r8d; int
0x180007c49  mov     rdx, rax; hWnd
0x180007c4c  call    ?OnInitProgressDialog@CEventUI@@AEAAJPEAUHWND__@@H@Z; CEventUI::OnInitProgressDialog(HWND__ *,int)
0x180007c51  mov     ebx, eax
0x180007c53  mov     eax, ebx
0x180007c55  mov     rbx, [rsp+28h+arg_0]
0x180007c5a  add     rsp, 20h
0x180007c5e  pop     rdi
0x180007c5f  retn
```
