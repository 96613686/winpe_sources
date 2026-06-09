# CColorBrowser::CreateHWND(HWND__ *)

- ea: `0x18000b890`
- end: `0x18000bada`
- name: `?CreateHWND@CColorBrowser@@MEAAPEAUHWND__@@PEAU2@@Z`
- size: `586`
- prototype: `HWND(CColorBrowser *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002f34`
- `0x18000af90`
- `0x18000b340`
- `0x18000b890`
- `0x18000be00`
- `0x18005528c`

## import_xrefs

- `UxTheme!IsThemeActive` at `0x18000b945`
- `UxTheme!IsThemeActive` at `0x18000b945`
- `UxTheme!SetWindowTheme` at `0x18000b966`
- `UxTheme!SetWindowTheme` at `0x18000b966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000baaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba96`
- `USER32!SendMessageW` at `0x18000b918`
- `USER32!SendMessageW` at `0x18000b939`
- `USER32!SendMessageW` at `0x18000ba51`
- `USER32!SendMessageW` at `0x18000ba82`
- `USER32!SendMessageW` at `0x18000b918`
- `USER32!SendMessageW` at `0x18000b939`
- `USER32!SendMessageW` at `0x18000ba51`
- `USER32!SendMessageW` at `0x18000ba82`
- `USER32!CreateWindowExW` at `0x18000b8eb`
- `USER32!CreateWindowExW` at `0x18000b8eb`

## pseudocode

```c
HWND __fastcall CColorBrowser::CreateHWND(CColorBrowser *this, HWND hWndParent)
{
  unsigned int v2; // esi
  HWND Window; // rax
  unsigned int *v5; // rbx
  struct _IMAGELIST *v6; // r14
  CColorBrowser *v7; // rcx
  unsigned int *v8; // r8
  int v9; // r12d
  unsigned int *v10; // rbp
  HWND v11; // rcx
  HANDLE ProcessHeap; // rax
  _DWORD lParam[10]; // [rsp+60h] [rbp-88h] BYREF
  __int64 v15; // [rsp+88h] [rbp-60h]
  LPVOID lpMem; // [rsp+F0h] [rbp+8h] BYREF

  v2 = 0;
  Window = CreateWindowExW(
             0x200u,
             L"SysListView32",
             &cchOriginalDestLength,
             0x5000030Cu,
             0,
             0,
             0,
             0,
             hWndParent,
             0,
             0,
             0);
  *((_QWORD *)this + 40) = Window;
  if ( Window )
  {
    SendMessageW(Window, 0x1036u, 0, 196608);
    SendMessageW(*((HWND *)this + 40), 0x1035u, 0, 5505108);
    if ( IsThemeActive() )
      SetWindowTheme(*((HWND *)this + 40), L"Explorer", 0);
    lpMem = 0;
    if ( (int)GetColors(&lpMem) >= 0 )
    {
      v5 = (unsigned int *)lpMem;
      v6 = ImageList_Create(60, 60, 0x21u, *(_DWORD *)lpMem & 0xFFFFFFF, 10);
      if ( v6 )
      {
        v7 = (CColorBrowser *)*v5;
        if ( ((unsigned int)v7 & 0xFFFFFFF) != 0 )
        {
          do
          {
            if ( ((unsigned int)v7 & 0x10000000) != 0 )
              v8 = (unsigned int *)*((_QWORD *)v5 + 1);
            else
              v8 = v5 + 2;
            v9 = CColorBrowser::AddColor(v7, v6, v8[v2]);
            if ( v9 != -1 )
            {
              if ( (*v5 & 0x10000000) != 0 )
                v10 = (unsigned int *)*((_QWORD *)v5 + 1);
              else
                v10 = v5 + 2;
              memset_0(lParam, 0, 0x58u);
              v11 = (HWND)*((_QWORD *)this + 40);
              v15 = v10[v2];
              lParam[0] = 6;
              lParam[9] = v9;
              lParam[1] = v2;
              SendMessageW(v11, 0x104Du, 0, (LPARAM)lParam);
            }
            v7 = (CColorBrowser *)*v5;
            ++v2;
          }
          while ( v2 < (*v5 & 0xFFFFFFF) );
        }
        SendMessageW(*((HWND *)this + 40), 0x1003u, 0, (LPARAM)v6);
      }
      DirectUI::DynamicArray<CColorSwatchConfig,0>::~DynamicArray<CColorSwatchConfig,0>(v5);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
  }
  return (HWND)*((_QWORD *)this + 40);
}

```

## disassembly

```asm
0x18000b890  mov     [rsp+arg_8], rbx
0x18000b895  mov     [rsp+arg_10], rbp
0x18000b89a  push    rsi
0x18000b89b  push    rdi
0x18000b89c  push    r12
0x18000b89e  push    r14
0x18000b8a0  push    r15
0x18000b8a2  sub     rsp, 0C0h
0x18000b8a9  xor     esi, esi
0x18000b8ab  lea     r8, cchOriginalDestLength; lpWindowName
0x18000b8b2  mov     [rsp+0E8h+lpParam], rsi; lpParam
0x18000b8b7  mov     rdi, rcx
0x18000b8ba  mov     [rsp+0E8h+hInstance], rsi; hInstance
0x18000b8bf  mov     r9d, 5000030Ch; dwStyle
0x18000b8c5  mov     [rsp+0E8h+hMenu], rsi; hMenu
0x18000b8ca  mov     ecx, 200h; dwExStyle
0x18000b8cf  mov     [rsp+0E8h+hWndParent], rdx; hWndParent
0x18000b8d4  lea     rdx, ClassName; "SysListView32"
0x18000b8db  mov     [rsp+0E8h+nHeight], esi; nHeight
0x18000b8df  mov     [rsp+0E8h+nWidth], esi; nWidth
0x18000b8e3  mov     [rsp+0E8h+Y], esi; Y
0x18000b8e7  mov     [rsp+0E8h+X], esi; X
0x18000b8eb  call    cs:__imp_CreateWindowExW
0x18000b8f2  nop     dword ptr [rax+rax+00h]
0x18000b8f7  mov     [rdi+140h], rax
0x18000b8fe  test    rax, rax
0x18000b901  jz      loc_18000BAB6
0x18000b907  mov     r9d, 30000h; lParam
0x18000b90d  xor     r8d, r8d; wParam
0x18000b910  mov     edx, 1036h; Msg
0x18000b915  mov     rcx, rax; hWnd
0x18000b918  call    cs:__imp_SendMessageW
0x18000b91f  nop     dword ptr [rax+rax+00h]
0x18000b924  mov     rcx, [rdi+140h]; hWnd
0x18000b92b  mov     r9d, 540054h; lParam
0x18000b931  xor     r8d, r8d; wParam
0x18000b934  mov     edx, 1035h; Msg
0x18000b939  call    cs:__imp_SendMessageW
0x18000b940  nop     dword ptr [rax+rax+00h]
0x18000b945  call    cs:__imp_IsThemeActive
0x18000b94c  nop     dword ptr [rax+rax+00h]
0x18000b951  test    eax, eax
0x18000b953  jz      short loc_18000B972
0x18000b955  mov     rcx, [rdi+140h]; hwnd
0x18000b95c  lea     rdx, pszSubAppName; "Explorer"
0x18000b963  xor     r8d, r8d; pszSubIdList
0x18000b966  call    cs:__imp_SetWindowTheme
0x18000b96d  nop     dword ptr [rax+rax+00h]
0x18000b972  lea     rcx, [rsp+0E8h+lpMem]
0x18000b97a  mov     [rsp+0E8h+lpMem], rsi
0x18000b982  call    ?GetColors@@YAJPEAPEAV?$DynamicArray@K$0A@@DirectUI@@@Z; GetColors(DirectUI::DynamicArray<ulong,0> * *)
0x18000b987  test    eax, eax
0x18000b989  js      loc_18000BAB6
0x18000b98f  mov     rbx, [rsp+0E8h+lpMem]
0x18000b997  mov     ecx, 3Ch ; '<'; cx
0x18000b99c  mov     edx, ecx; cy
0x18000b99e  mov     [rsp+0E8h+X], 0Ah; cGrow
0x18000b9a6  mov     r9d, [rbx]
0x18000b9a9  lea     r8d, [rcx-1Bh]; flags
0x18000b9ad  and     r9d, 0FFFFFFFh; cInitial
0x18000b9b4  call    ImageList_Create
0x18000b9b9  mov     r14, rax
0x18000b9bc  test    rax, rax
0x18000b9bf  jz      loc_18000BA8E
0x18000b9c5  mov     ecx, [rbx]; this
0x18000b9c7  test    ecx, 0FFFFFFFh
0x18000b9cd  jbe     loc_18000BA70
0x18000b9d3  bt      ecx, 1Ch
0x18000b9d7  jnb     short loc_18000B9DF
0x18000b9d9  mov     r8, [rbx+8]
0x18000b9dd  jmp     short loc_18000B9E3
0x18000b9df  lea     r8, [rbx+8]
0x18000b9e3  mov     r15d, esi
0x18000b9e6  mov     rdx, r14; struct _IMAGELIST *
0x18000b9e9  mov     r8d, [r8+r15*4]; unsigned int
0x18000b9ed  call    ?AddColor@CColorBrowser@@AEAAHPEAU_IMAGELIST@@K@Z; CColorBrowser::AddColor(_IMAGELIST *,ulong)
0x18000b9f2  mov     r12d, eax
0x18000b9f5  cmp     eax, 0FFFFFFFFh
0x18000b9f8  jz      short loc_18000BA5D
0x18000b9fa  test    dword ptr [rbx], 10000000h
0x18000ba00  jz      short loc_18000BA08
0x18000ba02  mov     rbp, [rbx+8]
0x18000ba06  jmp     short loc_18000BA0C
0x18000ba08  lea     rbp, [rbx+8]
0x18000ba0c  xor     edx, edx; Val
0x18000ba0e  lea     rcx, [rsp+0E8h+lParam]; void *
0x18000ba13  lea     r8d, [rdx+58h]; Size
0x18000ba17  call    memset_0
0x18000ba1c  mov     eax, [rbp+r15*4+0]
0x18000ba21  lea     r9, [rsp+0E8h+lParam]; lParam
0x18000ba26  mov     rcx, [rdi+140h]; hWnd
0x18000ba2d  xor     r8d, r8d; wParam
0x18000ba30  mov     edx, 104Dh; Msg
0x18000ba35  mov     [rsp+0E8h+var_60], rax
0x18000ba3d  mov     dword ptr [rsp+0E8h+lParam], 6
0x18000ba45  mov     [rsp+0E8h+var_64], r12d
0x18000ba4d  mov     dword ptr [rsp+0E8h+lParam+4], esi
0x18000ba51  call    cs:__imp_SendMessageW
0x18000ba58  nop     dword ptr [rax+rax+00h]
0x18000ba5d  mov     ecx, [rbx]
0x18000ba5f  inc     esi
0x18000ba61  mov     eax, ecx
0x18000ba63  and     eax, 0FFFFFFFh
0x18000ba68  cmp     esi, eax
0x18000ba6a  jb      loc_18000B9D3
0x18000ba70  mov     rcx, [rdi+140h]; hWnd
0x18000ba77  mov     r9, r14; lParam
0x18000ba7a  xor     r8d, r8d; wParam
0x18000ba7d  mov     edx, 1003h; Msg
0x18000ba82  call    cs:__imp_SendMessageW
0x18000ba89  nop     dword ptr [rax+rax+00h]
0x18000ba8e  mov     rcx, rbx
0x18000ba91  call    ??1?$DynamicArray@VCColorSwatchConfig@@$0A@@DirectUI@@QEAA@XZ; DirectUI::DynamicArray<CColorSwatchConfig,0>::~DynamicArray<CColorSwatchConfig,0>(void)
0x18000ba96  call    cs:__imp_GetProcessHeap
0x18000ba9d  nop     dword ptr [rax+rax+00h]
0x18000baa2  mov     r8, rbx; lpMem
0x18000baa5  xor     edx, edx; dwFlags
0x18000baa7  mov     rcx, rax; hHeap
0x18000baaa  call    cs:__imp_HeapFree
0x18000bab1  nop     dword ptr [rax+rax+00h]
0x18000bab6  mov     rax, [rdi+140h]
0x18000babd  lea     r11, [rsp+0E8h+var_28]
0x18000bac5  mov     rbx, [r11+38h]
0x18000bac9  mov     rbp, [r11+40h]
0x18000bacd  mov     rsp, r11
0x18000bad0  pop     r15
0x18000bad2  pop     r14
0x18000bad4  pop     r12
0x18000bad6  pop     rdi
0x18000bad7  pop     rsi
0x18000bad8  retn
```
