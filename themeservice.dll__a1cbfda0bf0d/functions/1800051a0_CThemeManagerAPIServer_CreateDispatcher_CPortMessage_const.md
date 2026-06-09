# CThemeManagerAPIServer::CreateDispatcher(CPortMessage const &)

- ea: `0x1800051a0`
- end: `0x180005297`
- name: `?CreateDispatcher@CThemeManagerAPIServer@@MEAAPEAVCAPIDispatcher@@AEBVCPortMessage@@@Z`
- size: `247`
- prototype: `struct CAPIDispatcher *__fastcall(CThemeManagerAPIServer *__hidden this, const struct CPortMessage *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800051a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000528c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000528c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005201`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005201`
- `ntdll!RtlInitializeCriticalSection` at `0x18000523e`
- `ntdll!RtlInitializeCriticalSection` at `0x18000525e`
- `ntdll!RtlInitializeCriticalSection` at `0x18000523e`
- `ntdll!RtlInitializeCriticalSection` at `0x18000525e`
- `ntdll!NtOpenProcess` at `0x1800051ec`
- `ntdll!NtOpenProcess` at `0x1800051ec`

## pseudocode

```c
struct CAPIDispatcher *__fastcall CThemeManagerAPIServer::CreateDispatcher(
        CThemeManagerAPIServer *this,
        const struct CPortMessage *a2)
{
  unsigned __int64 v2; // rax
  char *v3; // rax
  char *v4; // rbx
  HANDLE v5; // rdi
  unsigned __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES v8; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+10h] BYREF

  v2 = *((_QWORD *)a2 + 2);
  *(_QWORD *)&v8.Length = 48;
  memset(&v8.RootDirectory, 0, 40);
  hObject = 0;
  v7 = v2;
  if ( NtOpenProcess(&hObject, 0x1478u, &v8, (PCLIENT_ID)&v7) >= 0 )
  {
    v3 = (char *)LocalAlloc(0, 0xA8u);
    v4 = v3;
    if ( v3 )
    {
      v5 = hObject;
      *((_DWORD *)v3 + 2) = 1;
      v3[12] = 0;
      *(_QWORD *)v3 = &CAPIDispatcher::`vftable';
      *((_QWORD *)v3 + 2) = 0;
      *((_QWORD *)v3 + 3) = 0;
      *((_QWORD *)v3 + 4) = 0;
      *((_DWORD *)v3 + 10) = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v3 + 48));
      *((_QWORD *)v4 + 11) = 0;
      *((_QWORD *)v4 + 12) = v5;
      *((_QWORD *)v4 + 13) = 0;
      *((_WORD *)v4 + 56) = 0;
      *((_DWORD *)v4 + 30) = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v4 + 128));
      *(_QWORD *)v4 = &CThemeManagerDispatcher::`vftable';
      return (struct CAPIDispatcher *)v4;
    }
    CloseHandle(hObject);
  }
  return 0;
}

```

## disassembly

```asm
0x1800051a0  mov     r11, rsp
0x1800051a3  mov     [r11+18h], rbx
0x1800051a7  push    rsi
0x1800051a8  sub     rsp, 60h
0x1800051ac  mov     rax, [rdx+10h]
0x1800051b0  lea     r9, [r11-48h]; ClientId
0x1800051b4  xor     esi, esi
0x1800051b6  mov     qword ptr [r11-38h], 30h ; '0'
0x1800051be  xorps   xmm0, xmm0
0x1800051c1  mov     [r11-20h], rsi
0x1800051c5  mov     [r11-30h], rsi
0x1800051c9  lea     r8, [r11-38h]; ObjectAttributes
0x1800051cd  mov     [r11-28h], rsi
0x1800051d1  lea     rcx, [r11+10h]; ProcessHandle
0x1800051d5  mov     edx, 1478h; DesiredAccess
0x1800051da  mov     [r11+10h], rsi
0x1800051de  movdqu  [rsp+68h+var_18], xmm0
0x1800051e4  mov     [r11-48h], rax
0x1800051e8  mov     [r11-40h], rsi
0x1800051ec  call    cs:__imp_NtOpenProcess
0x1800051f2  test    eax, eax
0x1800051f4  js      loc_180005292
0x1800051fa  mov     edx, 0A8h; uBytes
0x1800051ff  xor     ecx, ecx; uFlags
0x180005201  call    cs:__imp_LocalAlloc
0x180005207  mov     rbx, rax
0x18000520a  test    rax, rax
0x18000520d  jz      short loc_180005287
0x18000520f  mov     [rsp+68h+arg_0], rdi
0x180005214  lea     rcx, [rbx+30h]; CriticalSection
0x180005218  mov     rdi, [rsp+68h+hObject]
0x18000521d  mov     dword ptr [rax+8], 1
0x180005224  mov     [rax+0Ch], sil
0x180005228  lea     rax, ??_7CAPIDispatcher@@6B@; const CAPIDispatcher::`vftable'
0x18000522f  mov     [rbx], rax
0x180005232  mov     [rbx+10h], rsi
0x180005236  mov     [rbx+18h], rsi
0x18000523a  mov     [rbx+20h], rsi
0x18000523e  call    cs:__imp_RtlInitializeCriticalSection
0x180005244  mov     [rbx+28h], eax
0x180005247  lea     rcx, [rbx+80h]; CriticalSection
0x18000524e  mov     [rbx+58h], rsi
0x180005252  mov     [rbx+60h], rdi
0x180005256  mov     [rbx+68h], rsi
0x18000525a  mov     [rbx+70h], si
0x18000525e  call    cs:__imp_RtlInitializeCriticalSection
0x180005264  mov     rdi, [rsp+68h+arg_0]
0x180005269  mov     [rbx+78h], eax
0x18000526c  lea     rax, ??_7CThemeManagerDispatcher@@6B@; const CThemeManagerDispatcher::`vftable'
0x180005273  mov     [rbx], rax
0x180005276  mov     rax, rbx
0x180005279  mov     rbx, [rsp+68h+arg_10]
0x180005281  add     rsp, 60h
0x180005285  pop     rsi
0x180005286  retn
0x180005287  mov     rcx, [rsp+68h+hObject]; hObject
0x18000528c  call    cs:__imp_CloseHandle
0x180005292  mov     rax, rsi
0x180005295  jmp     short loc_180005279
```
