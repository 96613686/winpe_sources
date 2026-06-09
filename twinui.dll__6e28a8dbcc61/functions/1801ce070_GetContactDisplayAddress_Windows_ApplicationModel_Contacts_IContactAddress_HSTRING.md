# GetContactDisplayAddress(Windows::ApplicationModel::Contacts::IContactAddress *,HSTRING__ * *)

- ea: `0x1801ce070`
- end: `0x1801ce1db`
- name: `?GetContactDisplayAddress@@YAJPEAUIContactAddress@Contacts@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801d0670`

## callees

- `0x1801ce070`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce0de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce19a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce1ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce0de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce122`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce19a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ce1ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce0c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce185`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce0c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce109`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1801ce185`

## pseudocode

```c
__int64 __fastcall GetContactDisplayAddress(
        struct Windows::ApplicationModel::Contacts::IContactAddress *a1,
        HSTRING *a2)
{
  __int64 v3; // rax
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  int v6; // ebx
  __int64 (__fastcall *v7)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 (__fastcall *v8)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 (__fastcall *v9)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  __int64 (__fastcall *v10)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *); // rbx
  HSTRING string; // [rsp+50h] [rbp+28h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)a1;
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(v3 + 48);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a1, &string);
  if ( v6 >= 0 )
  {
    if ( WindowsIsStringEmpty(string) )
    {
      v7 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 64LL);
      WindowsDeleteString(string);
      string = 0;
      v6 = v7(a1, &string);
      if ( v6 >= 0 )
      {
        if ( WindowsIsStringEmpty(string) )
        {
          v8 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 112LL);
          WindowsDeleteString(string);
          string = 0;
          v6 = v8(a1, &string);
          if ( v6 >= 0 )
          {
            if ( WindowsIsStringEmpty(string) )
            {
              v9 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 80LL);
              WindowsDeleteString(string);
              string = 0;
              v6 = v9(a1, &string);
              if ( v6 >= 0 )
              {
                if ( WindowsIsStringEmpty(string) )
                {
                  v10 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::Contacts::IContactAddress *, HSTRING *))(*(_QWORD *)a1 + 96LL);
                  WindowsDeleteString(string);
                  string = 0;
                  v6 = v10(a1, &string);
                }
              }
            }
          }
        }
      }
    }
  }
  *a2 = string;
  string = 0;
  WindowsDeleteString(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801ce070  push    rbp
0x1801ce072  push    rbx
0x1801ce073  push    rsi
0x1801ce074  push    rdi
0x1801ce075  mov     rbp, rsp
0x1801ce078  sub     rsp, 28h
0x1801ce07c  mov     qword ptr [rdx], 0
0x1801ce083  mov     rdi, rcx
0x1801ce086  mov     rax, [rcx]
0x1801ce089  mov     rsi, rdx
0x1801ce08c  xor     ecx, ecx; string
0x1801ce08e  mov     [rbp+string], 0
0x1801ce096  mov     rbx, [rax+30h]
0x1801ce09a  call    cs:__imp_WindowsDeleteString
0x1801ce0a0  lea     rdx, [rbp+string]
0x1801ce0a4  mov     [rbp+string], 0
0x1801ce0ac  mov     rcx, rdi
0x1801ce0af  mov     rax, rbx
0x1801ce0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce0b7  mov     ebx, eax
0x1801ce0b9  test    eax, eax
0x1801ce0bb  js      loc_1801CE1B9
0x1801ce0c1  mov     rcx, [rbp+string]; string
0x1801ce0c5  call    cs:__imp_WindowsIsStringEmpty
0x1801ce0cb  test    eax, eax
0x1801ce0cd  jz      loc_1801CE1B9
0x1801ce0d3  mov     rax, [rdi]
0x1801ce0d6  mov     rcx, [rbp+string]; string
0x1801ce0da  mov     rbx, [rax+40h]
0x1801ce0de  call    cs:__imp_WindowsDeleteString
0x1801ce0e4  lea     rdx, [rbp+string]
0x1801ce0e8  mov     [rbp+string], 0
0x1801ce0f0  mov     rcx, rdi
0x1801ce0f3  mov     rax, rbx
0x1801ce0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce0fb  mov     ebx, eax
0x1801ce0fd  test    eax, eax
0x1801ce0ff  js      loc_1801CE1B9
0x1801ce105  mov     rcx, [rbp+string]; string
0x1801ce109  call    cs:__imp_WindowsIsStringEmpty
0x1801ce10f  test    eax, eax
0x1801ce111  jz      loc_1801CE1B9
0x1801ce117  mov     rax, [rdi]
0x1801ce11a  mov     rcx, [rbp+string]; string
0x1801ce11e  mov     rbx, [rax+70h]
0x1801ce122  call    cs:__imp_WindowsDeleteString
0x1801ce128  lea     rdx, [rbp+string]
0x1801ce12c  mov     [rbp+string], 0
0x1801ce134  mov     rcx, rdi
0x1801ce137  mov     rax, rbx
0x1801ce13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce13f  mov     ebx, eax
0x1801ce141  test    eax, eax
0x1801ce143  js      short loc_1801CE1B9
0x1801ce145  mov     rcx, [rbp+string]; string
0x1801ce149  call    cs:__imp_WindowsIsStringEmpty
0x1801ce14f  test    eax, eax
0x1801ce151  jz      short loc_1801CE1B9
0x1801ce153  mov     rax, [rdi]
0x1801ce156  mov     rcx, [rbp+string]; string
0x1801ce15a  mov     rbx, [rax+50h]
0x1801ce15e  call    cs:__imp_WindowsDeleteString
0x1801ce164  lea     rdx, [rbp+string]
0x1801ce168  mov     [rbp+string], 0
0x1801ce170  mov     rcx, rdi
0x1801ce173  mov     rax, rbx
0x1801ce176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce17b  mov     ebx, eax
0x1801ce17d  test    eax, eax
0x1801ce17f  js      short loc_1801CE1B9
0x1801ce181  mov     rcx, [rbp+string]; string
0x1801ce185  call    cs:__imp_WindowsIsStringEmpty
0x1801ce18b  test    eax, eax
0x1801ce18d  jz      short loc_1801CE1B9
0x1801ce18f  mov     rax, [rdi]
0x1801ce192  mov     rcx, [rbp+string]; string
0x1801ce196  mov     rbx, [rax+60h]
0x1801ce19a  call    cs:__imp_WindowsDeleteString
0x1801ce1a0  lea     rdx, [rbp+string]
0x1801ce1a4  mov     [rbp+string], 0
0x1801ce1ac  mov     rcx, rdi
0x1801ce1af  mov     rax, rbx
0x1801ce1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ce1b7  mov     ebx, eax
0x1801ce1b9  mov     rax, [rbp+string]
0x1801ce1bd  xor     ecx, ecx; string
0x1801ce1bf  mov     [rsi], rax
0x1801ce1c2  mov     [rbp+string], 0
0x1801ce1ca  call    cs:__imp_WindowsDeleteString
0x1801ce1d0  mov     eax, ebx
0x1801ce1d2  add     rsp, 28h
0x1801ce1d6  pop     rdi
0x1801ce1d7  pop     rsi
0x1801ce1d8  pop     rbx
0x1801ce1d9  pop     rbp
0x1801ce1da  retn
```
