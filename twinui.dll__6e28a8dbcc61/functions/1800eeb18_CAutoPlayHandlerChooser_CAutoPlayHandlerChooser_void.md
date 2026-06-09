# CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(void)

- ea: `0x1800eeb18`
- end: `0x1800eebd9`
- name: `??1CAutoPlayHandlerChooser@@UEAA@XZ`
- size: `193`
- prototype: `void __fastcall(CAutoPlayHandlerChooser *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ff48`
- `0x18018b270`

## callees

- `0x18000b7e8`
- `0x1800eeb18`
- `0x1800eebe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800eeb9e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800eeb49`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800eeb49`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800eeb37`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800eeb37`

## pseudocode

```c
void __fastcall CAutoPlayHandlerChooser::~CAutoPlayHandlerChooser(CAutoPlayHandlerChooser *this)
{
  HWND v2; // rcx

  *(_QWORD *)this = &CAutoPlayHandlerChooser::`vftable';
  if ( *((_QWORD *)this + 36) )
    DevCloseObjectQuery();
  v2 = (HWND)*((_QWORD *)this + 20);
  if ( v2 )
    DestroyWindow(v2);
  CoTaskMemFree(*((LPVOID *)this + 2));
  CoTaskMemFree(*((LPVOID *)this + 3));
  CoTaskMemFree(*((LPVOID *)this + 31));
  CoTaskMemFree(*((LPVOID *)this + 32));
  CoTaskMemFree(*((LPVOID *)this + 33));
  CoTaskMemFree(*((LPVOID *)this + 38));
  CoTaskMemFree(*((LPVOID *)this + 39));
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 240);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 216);
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 208);
  CSafeElementListenerPtr<DirectUI::Element>::~CSafeElementListenerPtr<DirectUI::Element>((char *)this + 176);
}

```

## disassembly

```asm
0x1800eeb18  push    rbx
0x1800eeb1a  sub     rsp, 20h
0x1800eeb1e  lea     rax, ??_7CAutoPlayHandlerChooser@@6B@; const CAutoPlayHandlerChooser::`vftable'
0x1800eeb25  mov     rbx, rcx
0x1800eeb28  mov     [rcx], rax
0x1800eeb2b  mov     rcx, [rcx+120h]
0x1800eeb32  test    rcx, rcx
0x1800eeb35  jz      short loc_1800EEB3D
0x1800eeb37  call    cs:__imp_DevCloseObjectQuery
0x1800eeb3d  mov     rcx, [rbx+0A0h]; hWnd
0x1800eeb44  test    rcx, rcx
0x1800eeb47  jz      short loc_1800EEB4F
0x1800eeb49  call    cs:__imp_DestroyWindow
0x1800eeb4f  mov     rcx, [rbx+10h]; pv
0x1800eeb53  call    cs:__imp_CoTaskMemFree
0x1800eeb59  mov     rcx, [rbx+18h]; pv
0x1800eeb5d  call    cs:__imp_CoTaskMemFree
0x1800eeb63  mov     rcx, [rbx+0F8h]; pv
0x1800eeb6a  call    cs:__imp_CoTaskMemFree
0x1800eeb70  mov     rcx, [rbx+100h]; pv
0x1800eeb77  call    cs:__imp_CoTaskMemFree
0x1800eeb7d  mov     rcx, [rbx+108h]; pv
0x1800eeb84  call    cs:__imp_CoTaskMemFree
0x1800eeb8a  mov     rcx, [rbx+130h]; pv
0x1800eeb91  call    cs:__imp_CoTaskMemFree
0x1800eeb97  mov     rcx, [rbx+138h]; pv
0x1800eeb9e  call    cs:__imp_CoTaskMemFree
0x1800eeba4  lea     rcx, [rbx+0F0h]
0x1800eebab  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800eebb0  lea     rcx, [rbx+0D8h]
0x1800eebb7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800eebbc  lea     rcx, [rbx+0D0h]
0x1800eebc3  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800eebc8  lea     rcx, [rbx+0B0h]
0x1800eebcf  add     rsp, 20h
0x1800eebd3  pop     rbx
0x1800eebd4  jmp     ??1?$CSafeElementListenerPtr@VElement@DirectUI@@@@QEAA@XZ; CSafeElementListenerPtr<DirectUI::Element>::~CSafeElementListenerPtr<DirectUI::Element>(void)
```
