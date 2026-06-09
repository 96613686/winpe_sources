# Windows::System::Internal::UserManagerStatics::SignInSponsoredUser(uint,Windows::System::Internal::ISignInContext *,void *,Windows::System::Internal::ISignInResult * *)

- ea: `0x18009e47c`
- end: `0x1800a0122`
- name: `?SignInSponsoredUser@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAUISignInContext@234@PEAXPEAPEAUISignInResult@234@@Z`
- size: `7334`
- prototype: `__int64 __usercall@<rax>(Windows::System::Internal::UserManagerStatics *__hidden this@<rcx>, unsigned int@<edx>, struct Windows::System::Internal::ISignInContext *@<r8>, void *@<r9>, struct Windows::System::Internal::ISignInResult **)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009a4ec`

## callees

- `0x180006130`
- `0x180007920`
- `0x18000acdc`
- `0x18000ce48`
- `0x18000ed00`
- `0x180012890`
- `0x180015540`
- `0x1800179c0`
- `0x1800181f0`
- `0x180024828`
- `0x18002618c`
- `0x18002799c`
- `0x1800332e8`
- `0x18003559c`
- `0x180037c44`
- `0x18004b3d0`
- `0x18004ba28`
- `0x18004e77c`
- `0x18004fc2c`
- `0x180050c38`
- `0x1800513d0`
- `0x180060524`
- `0x1800624bc`
- `0x1800641b8`
- `0x1800653a8`
- `0x18008504c`
- `0x180086bcc`
- `0x18008a174`
- `0x18008c534`
- `0x18008cd68`
- `0x180092d74`
- `0x180092dd4`
- `0x18009e47c`
- `0x1800a6ddc`
- `0x1800c0008`
- `0x1800c0fe8`
- `0x1800de450`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e538`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009eaed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ec70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ec83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009eaed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ec70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ec83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e77a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e9bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ea05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009edb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009edcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ede1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009edf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ee0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ee23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f5c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f9cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fc8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fcc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e77a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009e9bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ea05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ed5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009edb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009edcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ede1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009edf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ee0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ee23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eebf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009eef1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f5c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f938`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009f9cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fa92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fb76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fba8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fc8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009fcc1`
- `ntdll!RtlIsMultiSessionSku` at `0x18009e721`
- `ntdll!RtlIsMultiSessionSku` at `0x18009e721`

## string_xrefs

- `0x18009fd33`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fd5a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fd6e`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fd82`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fd96`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fdaa`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fdbe`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fdd2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fde7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fdfc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe10`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe24`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe38`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe4c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe60`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe74`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe89`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fe9d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009feb2`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fec7`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fedc`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fef1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff06`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff1b`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff30`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff45`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff5a`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff6f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff84`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ff99`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ffad`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ffc1`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ffd5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009ffea`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009fffe`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0013`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0028`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a003d`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0052`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0067`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a007c`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a0091`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a00a6`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a00bb`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a00d0`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a00e5`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a00fa`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x1800a010f`: `onecore\ds\security\umstartup\usermgr\lib\usermanager.cpp`
- `0x18009f294`: `Privileges`

## pseudocode

```c
// Hidden C++ exception states: #wind=46 #try_helpers=1
__int64 __fastcall Windows::System::Internal::UserManagerStatics::SignInSponsoredUser(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2,
        struct Windows::System::Internal::ISignInContext *a3,
        void *a4,
        struct Windows::System::Internal::ISignInResult **a5)
{
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  __int16 v12; // bx
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *UserStaticsInternal; // r10
  int v14; // eax
  Windows::System::Internal::UserManagerStatics *v15; // rcx
  int SponsoredUserName; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  int v22; // eax
  int SponsoringUser; // eax
  HANDLE OwningThread; // rdi
  __int64 (__fastcall *v25)(HANDLE, _QWORD, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rbx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v38; // eax
  int v39; // eax
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, _QWORD, PCWSTR, PCWSTR); // rdi
  PCWSTR v42; // rbx
  PCWSTR v43; // rax
  Windows::System::Internal::UserManagerStatics *v45; // rcx
  int v46; // eax
  int v47; // eax
  int v48; // eax
  HSTRING v49; // rbx
  int v50; // eax
  HSTRING v51; // rbx
  int v52; // eax
  HSTRING v53; // rbx
  int v54; // eax
  HSTRING v55; // rbx
  int v56; // eax
  HSTRING v57; // rbx
  int v58; // eax
  HSTRING v59; // rbx
  int v60; // eax
  PVOID Reserved1; // rbx
  int v62; // eax
  PVOID v63; // rbx
  int v64; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v65; // r10
  int v66; // eax
  int v67; // eax
  int v68; // eax
  __int64 v69; // rsi
  __int64 (__fastcall *v70)(__int64, PCWSTR, __int64); // rdi
  __int64 v71; // rbx
  PCWSTR v72; // rax
  int v73; // eax
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v76; // eax
  int v77; // eax
  int v78; // eax
  int v79; // eax
  int v80; // eax
  int v81; // eax
  int v82; // eax
  HSTRING v83; // rbx
  int v84; // eax
  HSTRING v85; // rbx
  int v86; // eax
  HSTRING v87; // rbx
  int v88; // eax
  HSTRING v89; // rbx
  int v90; // eax
  __int64 v91; // rbx
  int v92; // eax
  HSTRING v93; // rbx
  int v94; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v95; // r10
  int v96; // eax
  struct Windows::System::Internal::Implementation::IUserStaticsInternal *v97; // rax
  int v98; // eax
  PCWSTR v99; // rax
  __int64 v100; // rcx
  const struct _tlgProvider_t *v101; // rax
  int v102; // r8d
  int v103; // r9d
  unsigned int v104; // eax
  int v105; // [rsp+20h] [rbp-318h]
  int v106; // [rsp+20h] [rbp-318h]
  _BYTE v107[8]; // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v108; // [rsp+78h] [rbp-2C0h] BYREF
  HSTRING string; // [rsp+80h] [rbp-2B8h] BYREF
  unsigned int v110; // [rsp+88h] [rbp-2B0h] BYREF
  HSTRING v111; // [rsp+90h] [rbp-2A8h] BYREF
  int v112; // [rsp+98h] [rbp-2A0h] BYREF
  HSTRING v113; // [rsp+A0h] [rbp-298h] BYREF
  unsigned int v114; // [rsp+A8h] [rbp-290h] BYREF
  __int64 v115; // [rsp+B0h] [rbp-288h] BYREF
  int v116[2]; // [rsp+B8h] [rbp-280h] BYREF
  __int64 (__fastcall ***v117)(_QWORD, GUID *, __int64); // [rsp+C0h] [rbp-278h] BYREF
  HSTRING v118; // [rsp+C8h] [rbp-270h] BYREF
  HSTRING v119; // [rsp+D0h] [rbp-268h] BYREF
  __int64 v120; // [rsp+D8h] [rbp-260h] BYREF
  Windows::System::Internal::SignInResult *v121; // [rsp+E0h] [rbp-258h] BYREF
  HSTRING v122; // [rsp+E8h] [rbp-250h] BYREF
  HSTRING v123; // [rsp+F0h] [rbp-248h] BYREF
  int v124[2]; // [rsp+F8h] [rbp-240h] BYREF
  HSTRING v125; // [rsp+100h] [rbp-238h] BYREF
  struct Windows::System::IUser *v126; // [rsp+108h] [rbp-230h] BYREF
  HSTRING v127; // [rsp+110h] [rbp-228h] BYREF
  HSTRING v128; // [rsp+118h] [rbp-220h] BYREF
  HSTRING v129; // [rsp+120h] [rbp-218h] BYREF
  int v130; // [rsp+128h] [rbp-210h] BYREF
  int v131; // [rsp+12Ch] [rbp-20Ch] BYREF
  int v132; // [rsp+130h] [rbp-208h] BYREF
  __int64 v133; // [rsp+138h] [rbp-200h] BYREF
  __int64 (__fastcall ***v134)(_QWORD, GUID *, __int64); // [rsp+140h] [rbp-1F8h] BYREF
  __int64 v135; // [rsp+148h] [rbp-1F0h] BYREF
  HSTRING v136; // [rsp+150h] [rbp-1E8h] BYREF
  __int64 v137; // [rsp+158h] [rbp-1E0h] BYREF
  __int64 (__fastcall ***v138)(_QWORD, GUID *, __int64); // [rsp+160h] [rbp-1D8h] BYREF
  __int64 v139; // [rsp+168h] [rbp-1D0h] BYREF
  __int64 v140; // [rsp+170h] [rbp-1C8h] BYREF
  void *v141; // [rsp+178h] [rbp-1C0h] BYREF
  const WCHAR *v142; // [rsp+180h] [rbp-1B8h] BYREF
  __int64 v143; // [rsp+188h] [rbp-1B0h]
  __int64 v144; // [rsp+190h] [rbp-1A8h]
  const WCHAR *v145; // [rsp+198h] [rbp-1A0h] BYREF
  __int64 v146; // [rsp+1A0h] [rbp-198h]
  __int64 v147; // [rsp+1A8h] [rbp-190h]
  __int64 v148; // [rsp+1B0h] [rbp-188h] BYREF
  __int64 v149; // [rsp+1B8h] [rbp-180h]
  __int64 v150; // [rsp+1C0h] [rbp-178h]
  __int64 v151; // [rsp+1C8h] [rbp-170h] BYREF
  __int64 v152; // [rsp+1D0h] [rbp-168h]
  __int64 v153; // [rsp+1D8h] [rbp-160h]
  __int64 v154; // [rsp+1E0h] [rbp-158h] BYREF
  __int64 v155; // [rsp+1E8h] [rbp-150h]
  __int64 v156; // [rsp+1F0h] [rbp-148h]
  __int64 v157; // [rsp+1F8h] [rbp-140h] BYREF
  __int64 v158; // [rsp+200h] [rbp-138h]
  __int64 v159; // [rsp+208h] [rbp-130h]
  __int64 v160; // [rsp+210h] [rbp-128h] BYREF
  __int64 v161; // [rsp+218h] [rbp-120h]
  __int64 v162; // [rsp+220h] [rbp-118h]
  int v163[2]; // [rsp+228h] [rbp-110h] BYREF
  __int64 v164; // [rsp+230h] [rbp-108h]
  __int64 v165; // [rsp+238h] [rbp-100h]
  struct Windows::System::Internal::ISignInResult **v166; // [rsp+240h] [rbp-F8h] BYREF
  _QWORD v167[7]; // [rsp+250h] [rbp-E8h] BYREF
  char v168; // [rsp+288h] [rbp-B0h]
  HSTRING_HEADER hstringHeader; // [rsp+290h] [rbp-A8h] BYREF
  __int64 v170; // [rsp+2A8h] [rbp-90h]
  HSTRING_HEADER v171; // [rsp+2B0h] [rbp-88h] BYREF
  __int64 v172; // [rsp+2C8h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v114 = a2;
  v166 = a5;
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(*(unsigned __int8 (__fastcall **)(ULONG_PTR *))(this[13].SpinCount + 8))(&this[13].SpinCount) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v9 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v9 > 4u )
  {
    v110 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (_DWORD)v9,
      (unsigned int)&unk_180125170,
      v10,
      v11,
      (__int64)&v110);
  }
  if ( a2 - 1 > 0xE )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(this + 11);
  *(_QWORD *)v124 = this + 11;
  v12 = LOWORD(this[12].DebugInfo) & (1 << (a2 - 1));
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v124);
  if ( !v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x155C,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)0x80070057LL,
      v105);
  v112 = 0;
  v132 = 0;
  v131 = 0;
  *(_QWORD *)v116 = 0;
  v135 = 0;
  v121 = 0;
  v115 = 0;
  string = 0;
  v134 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v134);
  v133 = 0;
  v130 = 0;
  v111 = 0;
  *(_QWORD *)v163 = 0;
  v164 = 0;
  v165 = 0;
  v160 = 0;
  v161 = 0;
  v162 = 0;
  v157 = 0;
  v158 = 0;
  v159 = 0;
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  v148 = 0;
  v149 = 0;
  v150 = 0;
  v145 = 0;
  v146 = 0;
  v147 = 0;
  v142 = 0;
  v143 = 0;
  v144 = 0;
  *v166 = 0;
  v167[0] = &v131;
  v167[1] = &v115;
  v167[2] = &v121;
  v167[3] = &v132;
  v167[4] = &v112;
  v167[5] = &v166;
  v167[6] = this;
  v168 = 1;
  if ( (unsigned __int8)RtlIsMultiSessionSku() )
  {
    v104 = wil::verify_hresult<long>(2147942450LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x159D,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)v104,
      v105);
  }
  UserStaticsInternal = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)this);
  v14 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)UserStaticsInternal + 136LL))(
          UserStaticsInternal,
          a2,
          0,
          0);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15A1,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v14,
      (int)v116);
  WindowsDeleteString(string);
  string = 0;
  SponsoredUserName = Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(v15, a2, &string);
  if ( SponsoredUserName < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15A4,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)SponsoredUserName,
      (int)v116);
  v17 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::ISignInContext *, int *))(*(_QWORD *)a3 + 64LL))(
          a3,
          &v130);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15A5,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v17,
      (int)v116);
  v18 = Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::ISignInContext2>(
          &v134,
          (__int64)&v133);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15A9,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v18,
      (int)v116);
  v19 = v133;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v133 + 48LL);
  WindowsDeleteString(v111);
  v111 = 0;
  v21 = v20(v19, &v111);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15AA,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v21,
      (int)v116);
  *(_QWORD *)v124 = v111;
  v141 = string;
  v22 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,unsigned int &,HSTRING__ *,enum Windows::System::Internal::SignInCaller &,HSTRING__ *>(
          (unsigned int)&v121,
          (unsigned int)&v114,
          (unsigned int)&v141,
          (unsigned int)&v130,
          (__int64)v124);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15AD,
      (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
      (const char *)(unsigned int)v22,
      v106);
  if ( *(_QWORD *)v116 )
  {
    if ( (byte_180147C81 & 1) != 0 )
      McTemplateU0p_EventWriteTransfer(retaddr);
  }
  else
  {
    v141 = 0;
    v110 = 0;
    v113 = 0;
    v123 = 0;
    v122 = 0;
    v129 = 0;
    v128 = 0;
    v127 = 0;
    v126 = 0;
    v140 = 0;
    v139 = 0;
    v117 = 0;
    v108 = 0;
    v107[0] = 0;
    *(_QWORD *)v124 = 0;
    SponsoringUser = Windows::System::Internal::UserManagerStatics::GetSponsoringUser(
                       (Windows::System::Internal::UserManagerStatics *)this,
                       &v110,
                       &v126);
    if ( SponsoringUser < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15BD,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)SponsoringUser,
        v106);
    v119 = 0;
    v118 = 0;
    v120 = 0;
    OwningThread = this[13].OwningThread;
    v25 = *(__int64 (__fastcall **)(HANDLE, _QWORD, __int64 *))(*(_QWORD *)OwningThread + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
    v26 = v25(OwningThread, v110, &v120);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15C3,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v26,
        v106);
    v27 = v120;
    v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v120 + 64LL);
    WindowsDeleteString(v119);
    v119 = 0;
    v29 = v28(v27, &v119);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15C5,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v29,
        v106);
    v30 = v120;
    v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v120 + 56LL);
    WindowsDeleteString(v118);
    v118 = 0;
    v32 = v31(v30, &v118);
    if ( v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15C6,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v32,
        v106);
    v33 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(retaddr, a4);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15C8,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v33,
        v106);
    v34 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v126,
            &v140);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15CA,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v34,
        v106);
    v35 = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v140 + 80LL))(v140, &v141);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15CC,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v35,
        v106);
    if ( Windows::System::Internal::UserManagerStatics::IsConnectedToXboxLive((Windows::System::Internal::UserManagerStatics *)this) )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
      v36 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(
              &this[13].SpinCount,
              &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
              &v115);
      if ( v36 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15D0,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v36,
          v106);
      StringRawBuffer = WindowsGetStringRawBuffer(v118, 0);
      Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(
        (Windows::System::Internal::Implementation::AutoUserContext *)&v171,
        v141,
        StringRawBuffer);
      v38 = Microsoft::WRL::ComPtr<Windows::System::Internal::SignInResult>::As<IUserAuthenticationCallback>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v121,
              (__int64)&v139);
      if ( v38 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15D5,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v38,
          v106);
      v39 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v115 + 152LL))(v115, v139, &v131);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15D6,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v39,
          v106);
      v40 = v115;
      v41 = *(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, PCWSTR))(*(_QWORD *)v115 + 616LL);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v142);
      v143 = -1;
      v144 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v145);
      v146 = -1;
      v147 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v148);
      v149 = -1;
      v150 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
      v152 = -1;
      v153 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v154);
      v155 = -1;
      v156 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v157);
      v158 = -1;
      v159 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v160);
      v161 = -1;
      v162 = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v163);
      v164 = -1;
      v165 = -1;
      v42 = WindowsGetStringRawBuffer(v119, 0);
      v43 = WindowsGetStringRawBuffer(string, 0);
      v132 = v41(v40, a2, v43, v42);
      if ( v132 < 0 )
      {
        Windows::System::Internal::SignInResult::WaitForUserAuthenticationFailure(v121);
        Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)&v171);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
        WindowsDeleteString(v118);
        v118 = 0;
        WindowsDeleteString(v119);
        v119 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v108);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v139);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v126);
        WindowsDeleteString(v127);
        v127 = 0;
        WindowsDeleteString(v128);
        v128 = 0;
        WindowsDeleteString(v129);
        v129 = 0;
        WindowsDeleteString(v122);
        v122 = 0;
        WindowsDeleteString(v123);
        v123 = 0;
        WindowsDeleteString(v113);
        v113 = 0;
        v168 = 0;
        lambda_37e1e282b86e66f7e5ca6a5cce3c333d_::operator()(v167);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v142);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v145);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v148);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v154);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v157);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v160);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v163);
        WindowsDeleteString(v111);
        v111 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v116);
        return 0;
      }
      Windows::System::Internal::Implementation::AutoUserContext::Revoke((Windows::System::Internal::Implementation::AutoUserContext *)&v171);
      v46 = Windows::System::Internal::UserManagerStatics::CheckCancelEvent(v45, a4);
      if ( v46 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15F1,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v46,
          (int)v163);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(&v113);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(&v123);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(&v122);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(&v129);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(&v127);
      Microsoft::WRL::Wrappers::HString::Set<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>(&v128);
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Collections.PropertySet",
        0x2Bu,
        0x2Au);
      v47 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
              v170,
              &v117);
      if ( v47 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15FC,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v47,
          (int)v163);
      v48 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v117,
              (__int64)&v108);
      if ( v48 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x15FE,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v48,
          (int)v163);
      v49 = v128;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UserData", 9u, 8u);
      v50 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v49,
              (__int64)v107);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1600,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v50,
          (int)v163);
      v51 = v127;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
      v52 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v51,
              (__int64)v107);
      if ( v52 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1601,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v52,
          (int)v163);
      v53 = v113;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
      v54 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v53,
              (__int64)v107);
      if ( v54 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1602,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v54,
          (int)v163);
      v55 = v123;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
      v56 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v55,
              (__int64)v107);
      if ( v56 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1603,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v56,
          (int)v163);
      v57 = v122;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertagSuffix", 0x15u, 0x14u);
      v58 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v57,
              (__int64)v107);
      if ( v58 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1604,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v58,
          (int)v163);
      v59 = v129;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UniqueModernGamertag", 0x15u, 0x14u);
      v60 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v59,
              (__int64)v107);
      if ( v60 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1605,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v60,
          (int)v163);
      Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v171, &v145)[1].Reserved.Reserved1;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Privileges", 0xBu, 0xAu);
      v62 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)Reserved1,
              (__int64)v107);
      if ( v62 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1606,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v62,
          (int)v163);
      v63 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v171, &v142)[1].Reserved.Reserved1;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
      v64 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v63,
              (__int64)v107);
      if ( v64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1607,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v64,
          (int)v163);
      v65 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)this);
      v66 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v65 + 96LL))(
              v65,
              a2,
              string,
              0);
      if ( v66 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1615,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v66,
          0);
      v67 = Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(
              (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v116,
              &v135);
      if ( v67 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1617,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v67,
          0);
      v68 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v135 + 88LL))(v135, v124);
      if ( v68 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1618,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v68,
          0);
      v69 = v115;
      v70 = *(__int64 (__fastcall **)(__int64, PCWSTR, __int64))(*(_QWORD *)v115 + 432LL);
      v71 = *(_QWORD *)v124;
      v72 = WindowsGetStringRawBuffer(string, 0);
      v73 = v70(v69, v72, v71);
      if ( v73 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1619,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v73,
          0);
    }
    else
    {
      v136 = 0;
      v138 = 0;
      v137 = 0;
      v125 = 0;
      v74 = v120;
      v75 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v120
                                                                                                  + 88LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
      v76 = v75(v74, &v138);
      if ( v76 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1623,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v76,
          v106);
      v77 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v138,
              (__int64)&v137);
      if ( v77 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1624,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v77,
          v106);
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Collections.PropertySet",
        0x2Bu,
        0x2Au);
      v78 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
              v170,
              &v117);
      if ( v78 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1628,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v78,
          v106);
      v79 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
              &v117,
              (__int64)&v108);
      if ( v79 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x162A,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v79,
          v106);
      WindowsDeleteString(v136);
      v136 = 0;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
      v80 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
              v137,
              v170,
              (__int64)&v136);
      if ( v80 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x162B,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v80,
          v106);
      WindowsDeleteString(v125);
      v125 = 0;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
      v81 = Windows::System::Internal::Implementation::ComUtils::FromPropertyMap<HSTRING__ *>(
              v137,
              v170,
              (__int64)&v125);
      if ( v81 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x162C,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v81,
          v106);
      v82 = Windows::System::Internal::UserManagerStatics::ConstructGamertagForSponsoredUser(
              retaddr,
              a2,
              v136,
              (struct Microsoft::WRL::Wrappers::HString *)&v113);
      if ( v82 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x162F,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v82,
          v106);
      v83 = string;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"XboxUserId", 0xBu, 0xAu);
      v84 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v83,
              (__int64)v107);
      if ( v84 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1631,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v84,
          v106);
      v85 = v113;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Gamertag", 9u, 8u);
      v86 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v85,
              (__int64)v107);
      if ( v86 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1632,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v86,
          v106);
      v87 = v125;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"AgeGroup", 9u, 8u);
      v88 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v87,
              (__int64)v107);
      if ( v88 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1633,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v88,
          v106);
      v89 = v113;
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ModernGamertag", 0xFu, 0xEu);
      v90 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v170,
              (__int64)v89,
              (__int64)v107);
      if ( v90 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1636,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v90,
          v106);
      v170 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &cchOriginalDestLength, 1u, 0);
      v91 = v170;
      v172 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v171, L"ModernGamertagSuffix", 0x15u, 0x14u);
      v92 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v172,
              v91,
              (__int64)v107);
      if ( v92 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1637,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v92,
          v106);
      v93 = v113;
      v172 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v171, L"UniqueModernGamertag", 0x15u, 0x14u);
      v94 = Windows::System::Internal::Implementation::ComUtils::IntoPropertyMap<HSTRING__ *>(
              v108,
              v172,
              (__int64)v93,
              (__int64)v107);
      if ( v94 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1638,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v94,
          v106);
      v95 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)this);
      v96 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v95 + 96LL))(
              v95,
              a2,
              string,
              0);
      if ( v96 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1646,
          (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
          (const char *)(unsigned int)v96,
          0);
      WindowsDeleteString(v125);
      v125 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v137);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v138);
      WindowsDeleteString(v136);
    }
    v97 = Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal((Windows::System::Internal::UserManagerStatics *)this);
    v98 = (*(__int64 (__fastcall **)(struct Windows::System::Internal::Implementation::IUserStaticsInternal *, _QWORD, _QWORD))(*(_QWORD *)v97 + 208LL))(
            v97,
            *(_QWORD *)v116,
            0);
    if ( v98 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x164A,
        (unsigned int)"onecore\\ds\\security\\umstartup\\usermgr\\lib\\usermanager.cpp",
        (const char *)(unsigned int)v98,
        0);
    if ( (byte_180147C81 & 1) != 0 )
    {
      v99 = WindowsGetStringRawBuffer(string, 0);
      McTemplateU0z_EventWriteTransfer(v100, SignInHelper_Log_NewUser, v99);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v120);
    WindowsDeleteString(v118);
    v118 = 0;
    WindowsDeleteString(v119);
    v119 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v108);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v117);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v139);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v140);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v126);
    WindowsDeleteString(v127);
    v127 = 0;
    WindowsDeleteString(v128);
    v128 = 0;
    WindowsDeleteString(v129);
    v129 = 0;
    WindowsDeleteString(v122);
    v122 = 0;
    WindowsDeleteString(v123);
    v123 = 0;
    WindowsDeleteString(v113);
  }
  v101 = UserMgrUserModelTelemetry::Provider();
  if ( *(_DWORD *)v101 > 4u )
  {
    v110 = 0;
    LODWORD(v108) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v101,
      (unsigned int)&byte_180125127,
      v102,
      v103,
      (__int64)&v108,
      (__int64)&v110);
  }
  v168 = 0;
  lambda_37e1e282b86e66f7e5ca6a5cce3c333d_::operator()(v167);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v142);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v145);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v148);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v151);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v154);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v157);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v160);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v163);
  WindowsDeleteString(v111);
  v111 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v133);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v134);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v115);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v121);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v135);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v116);
  return 0;
}

```

## disassembly

```asm
0x18009e47c  push    rbx
0x18009e47e  push    rsi
0x18009e47f  push    rdi
0x18009e480  push    r12
0x18009e482  push    r13
0x18009e484  push    r14
0x18009e486  push    r15
0x18009e488  sub     rsp, 300h
0x18009e48f  mov     rax, cs:__security_cookie
0x18009e496  xor     rax, rsp
0x18009e499  mov     [rsp+338h+var_48], rax
0x18009e4a1  mov     r12, r9
0x18009e4a4  mov     rdi, r8
0x18009e4a7  mov     r13d, edx
0x18009e4aa  mov     r15, rcx
0x18009e4ad  mov     rax, [rsp+338h+arg_20]
0x18009e4b5  mov     [rsp+338h+var_290], edx
0x18009e4bc  mov     [rsp+338h+var_F8], rax
0x18009e4c4  xor     r14d, r14d
0x18009e4c7  test    rax, rax
0x18009e4ca  jnz     short loc_18009E4D1
0x18009e4cc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e4d1  lea     rsi, [r15+228h]
0x18009e4d8  mov     rax, [rsi]
0x18009e4db  mov     rcx, rsi
0x18009e4de  mov     rax, [rax+8]
0x18009e4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e4e7  test    al, al
0x18009e4e9  jnz     short loc_18009E4F0
0x18009e4eb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e4f0  call    ?Provider@UserMgrUserModelTelemetry@@SAPEBU_tlgProvider_t@@XZ; UserMgrUserModelTelemetry::Provider(void)
0x18009e4f5  mov     ecx, [rax]
0x18009e4f7  cmp     ecx, 4
0x18009e4fa  jbe     short loc_18009E520
0x18009e4fc  mov     [rsp+338h+var_2B0], r13d
0x18009e504  lea     rcx, [rsp+338h+var_2B0]
0x18009e50c  mov     qword ptr [rsp+338h+var_318], rcx; int
0x18009e511  lea     rdx, unk_180125170
0x18009e518  mov     rcx, rax
0x18009e51b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009e520  lea     eax, [r13-1]
0x18009e524  cmp     eax, 0Eh
0x18009e527  jbe     short loc_18009E52E
0x18009e529  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009e52e  lea     rbx, [r15+1B8h]
0x18009e535  mov     rcx, rbx; lpCriticalSection
0x18009e538  call    cs:__imp_EnterCriticalSection
0x18009e53e  mov     qword ptr [rsp+338h+var_240], rbx
0x18009e546  lea     ecx, [r13-1]
0x18009e54a  mov     ebx, 1
0x18009e54f  shl     bx, cl
0x18009e552  and     bx, [r15+1E0h]
0x18009e55a  lea     rcx, [rsp+338h+var_240]; this
0x18009e562  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x18009e567  mov     rcx, [rsp+338h]; this
0x18009e56f  test    bx, bx
0x18009e572  jz      loc_18009FD2D
0x18009e578  mov     [rsp+338h+var_2A0], r14d
0x18009e580  mov     [rsp+338h+var_208], r14d
0x18009e588  mov     [rsp+338h+var_20C], r14d
0x18009e590  mov     qword ptr [rsp+338h+var_280], r14
0x18009e598  mov     [rsp+338h+var_1F0], r14
0x18009e5a0  mov     [rsp+338h+var_258], r14
0x18009e5a8  mov     [rsp+338h+var_288], r14
0x18009e5b0  mov     [rsp+338h+string], r14
0x18009e5b8  mov     [rsp+338h+var_1F8], rdi
0x18009e5c0  lea     rcx, [rsp+338h+var_1F8]
0x18009e5c8  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009e5cd  nop
0x18009e5ce  mov     [rsp+338h+var_200], r14
0x18009e5d6  mov     [rsp+338h+var_210], r14d
0x18009e5de  mov     [rsp+338h+var_2A8], r14
0x18009e5e6  mov     qword ptr [rsp+338h+var_110], r14
0x18009e5ee  mov     [rsp+338h+var_108], r14
0x18009e5f6  mov     [rsp+338h+var_100], r14
0x18009e5fe  mov     [rsp+338h+var_128], r14
0x18009e606  mov     [rsp+338h+var_120], r14
0x18009e60e  mov     [rsp+338h+var_118], r14
0x18009e616  mov     [rsp+338h+var_140], r14
0x18009e61e  mov     [rsp+338h+var_138], r14
0x18009e626  mov     [rsp+338h+var_130], r14
0x18009e62e  mov     [rsp+338h+var_158], r14
0x18009e636  mov     [rsp+338h+var_150], r14
0x18009e63e  mov     [rsp+338h+var_148], r14
0x18009e646  mov     [rsp+338h+var_170], r14
0x18009e64e  mov     [rsp+338h+var_168], r14
0x18009e656  mov     [rsp+338h+var_160], r14
0x18009e65e  mov     [rsp+338h+var_188], r14
0x18009e666  mov     [rsp+338h+var_180], r14
0x18009e66e  mov     [rsp+338h+var_178], r14
0x18009e676  mov     [rsp+338h+var_1A0], r14
0x18009e67e  mov     [rsp+338h+var_198], r14
0x18009e686  mov     [rsp+338h+var_190], r14
0x18009e68e  mov     [rsp+338h+var_1B8], r14
0x18009e696  mov     [rsp+338h+var_1B0], r14
0x18009e69e  mov     [rsp+338h+var_1A8], r14
0x18009e6a6  mov     rax, [rsp+338h+var_F8]
0x18009e6ae  mov     [rax], r14
0x18009e6b1  lea     rax, [rsp+338h+var_20C]
0x18009e6b9  mov     [rsp+338h+var_E8], rax
0x18009e6c1  lea     rax, [rsp+338h+var_288]
0x18009e6c9  mov     [rsp+338h+var_E0], rax
0x18009e6d1  lea     rax, [rsp+338h+var_258]
0x18009e6d9  mov     [rsp+338h+var_D8], rax
0x18009e6e1  lea     rax, [rsp+338h+var_208]
0x18009e6e9  mov     [rsp+338h+var_D0], rax
0x18009e6f1  lea     rax, [rsp+338h+var_2A0]
0x18009e6f9  mov     [rsp+338h+var_C8], rax
0x18009e701  lea     rax, [rsp+338h+var_F8]
0x18009e709  mov     [rsp+338h+var_C0], rax
0x18009e711  mov     [rsp+338h+var_B8], r15
0x18009e719  mov     [rsp+338h+var_B0], 1
0x18009e721  call    cs:__imp_RtlIsMultiSessionSku
0x18009e727  test    al, al
0x18009e729  jnz     loc_18009FD45
0x18009e72f  mov     rcx, r15; this
0x18009e732  call    ?GetUserStaticsInternal@UserManagerStatics@Internal@System@Windows@@AEAAPEAUIUserStaticsInternal@Implementation@234@XZ; Windows::System::Internal::UserManagerStatics::GetUserStaticsInternal(void)
0x18009e737  mov     r10, rax
0x18009e73a  mov     rcx, [rax]
0x18009e73d  mov     rax, [rcx+88h]
0x18009e744  lea     rcx, [rsp+338h+var_280]
0x18009e74c  mov     qword ptr [rsp+338h+var_318], rcx; int
0x18009e751  xor     r9d, r9d
0x18009e754  xor     r8d, r8d
0x18009e757  mov     edx, r13d
0x18009e75a  mov     rcx, r10
0x18009e75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e762  mov     rcx, [rsp+338h]; this
0x18009e76a  test    eax, eax
0x18009e76c  js      loc_18009FD6B
0x18009e772  mov     rcx, [rsp+338h+string]; string
0x18009e77a  call    cs:__imp_WindowsDeleteString
0x18009e780  mov     [rsp+338h+string], r14
0x18009e788  lea     r8, [rsp+338h+string]; HSTRING *
0x18009e790  mov     edx, r13d; unsigned int
0x18009e793  call    ?GetSponsoredUserName@UserManagerStatics@Internal@System@Windows@@AEAAJIPEAPEAUHSTRING__@@@Z; Windows::System::Internal::UserManagerStatics::GetSponsoredUserName(uint,HSTRING__ * *)
0x18009e798  mov     rcx, [rsp+338h]; this
0x18009e7a0  test    eax, eax
0x18009e7a2  js      loc_18009FD7F
0x18009e7a8  mov     rax, [rdi]
0x18009e7ab  lea     rdx, [rsp+338h+var_210]
0x18009e7b3  mov     rcx, rdi
0x18009e7b6  mov     rax, [rax+40h]
0x18009e7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e7bf  mov     rcx, [rsp+338h]; this
0x18009e7c7  test    eax, eax
0x18009e7c9  js      loc_18009FD93
0x18009e7cf  lea     rdx, [rsp+338h+var_200]
0x18009e7d7  lea     rcx, [rsp+338h+var_1F8]
0x18009e7df  call    ??$As@UISignInContext2@Internal@System@Windows@@@?$ComPtr@UISignInContext@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISignInContext2@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext>::As<Windows::System::Internal::ISignInContext2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::ISignInContext2>>)
0x18009e7e4  mov     rcx, [rsp+338h]; this
0x18009e7ec  test    eax, eax
0x18009e7ee  js      loc_18009FDA7
0x18009e7f4  mov     rdi, [rsp+338h+var_200]
0x18009e7fc  mov     rax, [rdi]
0x18009e7ff  mov     rbx, [rax+30h]
0x18009e803  mov     rcx, [rsp+338h+var_2A8]; string
0x18009e80b  call    cs:__imp_WindowsDeleteString
0x18009e811  mov     [rsp+338h+var_2A8], r14
0x18009e819  lea     rdx, [rsp+338h+var_2A8]
0x18009e821  mov     rcx, rdi
0x18009e824  mov     rax, rbx
0x18009e827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e82c  mov     rcx, [rsp+338h]; this
0x18009e834  test    eax, eax
0x18009e836  js      loc_18009FDBB
0x18009e83c  mov     rax, [rsp+338h+var_2A8]
0x18009e844  mov     qword ptr [rsp+338h+var_240], rax
0x18009e84c  mov     rax, [rsp+338h+string]
0x18009e854  mov     [rsp+338h+var_1C0], rax
0x18009e85c  lea     rax, [rsp+338h+var_240]
0x18009e864  mov     qword ptr [rsp+338h+var_318], rax; int
0x18009e869  lea     r9, [rsp+338h+var_210]
0x18009e871  lea     r8, [rsp+338h+var_1C0]
0x18009e879  lea     rdx, [rsp+338h+var_290]
0x18009e881  lea     rcx, [rsp+338h+var_258]
0x18009e889  call    ??$MakeAndInitialize@VSignInResult@Internal@System@Windows@@V1234@AEAIPEAUHSTRING__@@AEAW4SignInCaller@234@PEAU5@@Details@WRL@Microsoft@@YAJPEAPEAVSignInResult@Internal@System@Windows@@AEAI$$QEAPEAUHSTRING__@@AEAW4SignInCaller@456@2@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::SignInResult,Windows::System::Internal::SignInResult,uint &,HSTRING__ *,Windows::System::Internal::SignInCaller &,HSTRING__ *>(Windows::System::Internal::SignInResult * *,uint &,HSTRING__ * &&,Windows::System::Internal::SignInCaller &,HSTRING__ * &&)
0x18009e88e  mov     rcx, [rsp+338h]; this
0x18009e896  test    eax, eax
0x18009e898  js      loc_18009FDCF
0x18009e89e  mov     r8, qword ptr [rsp+338h+var_280]
0x18009e8a6  test    r8, r8
0x18009e8a9  jnz     loc_18009FA9A
0x18009e8af  mov     [rsp+338h+var_1C0], r14
0x18009e8b7  mov     [rsp+338h+var_2B0], r14d
0x18009e8bf  mov     [rsp+338h+var_298], r14
0x18009e8c7  mov     [rsp+338h+var_248], r14
0x18009e8cf  mov     [rsp+338h+var_250], r14
0x18009e8d7  mov     [rsp+338h+var_218], r14
0x18009e8df  mov     [rsp+338h+var_220], r14
0x18009e8e7  mov     [rsp+338h+var_228], r14
0x18009e8ef  mov     [rsp+338h+var_230], r14
0x18009e8f7  mov     [rsp+338h+var_1C8], r14
0x18009e8ff  mov     [rsp+338h+var_1D0], r14
0x18009e907  mov     [rsp+338h+var_278], r14
0x18009e90f  mov     [rsp+338h+var_2C0], r14
0x18009e914  mov     [rsp+338h+var_2C8], r14b
0x18009e919  mov     qword ptr [rsp+338h+var_240], r14
0x18009e921  lea     r8, [rsp+338h+var_230]; struct Windows::System::IUser **
0x18009e929  lea     rdx, [rsp+338h+var_2B0]; unsigned int *
0x18009e931  mov     rcx, r15; this
0x18009e934  call    ?GetSponsoringUser@UserManagerStatics@Internal@System@Windows@@AEAAJPEAIPEAPEAUIUser@34@@Z; Windows::System::Internal::UserManagerStatics::GetSponsoringUser(uint *,Windows::System::IUser * *)
0x18009e939  mov     rcx, [rsp+338h]; this
0x18009e941  test    eax, eax
0x18009e943  js      loc_18009FDE4
0x18009e949  mov     [rsp+338h+var_268], r14
0x18009e951  mov     [rsp+338h+var_270], r14
0x18009e959  mov     [rsp+338h+var_260], r14
0x18009e961  mov     rdi, [r15+218h]
0x18009e968  mov     rax, [rdi]
0x18009e96b  mov     rbx, [rax+60h]
0x18009e96f  lea     rcx, [rsp+338h+var_260]
0x18009e977  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009e97c  lea     r8, [rsp+338h+var_260]
0x18009e984  mov     edx, [rsp+338h+var_2B0]
0x18009e98b  mov     rcx, rdi
0x18009e98e  mov     rax, rbx
0x18009e991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e996  mov     rcx, [rsp+338h]; this
0x18009e99e  test    eax, eax
0x18009e9a0  js      loc_18009FDF9
0x18009e9a6  mov     rdi, [rsp+338h+var_260]
0x18009e9ae  mov     rax, [rdi]
0x18009e9b1  mov     rbx, [rax+40h]
0x18009e9b5  mov     rcx, [rsp+338h+var_268]; string
0x18009e9bd  call    cs:__imp_WindowsDeleteString
0x18009e9c3  mov     [rsp+338h+var_268], r14
0x18009e9cb  lea     rdx, [rsp+338h+var_268]
0x18009e9d3  mov     rcx, rdi
0x18009e9d6  mov     rax, rbx
0x18009e9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e9de  mov     rcx, [rsp+338h]; this
0x18009e9e6  test    eax, eax
0x18009e9e8  js      loc_18009FE0D
0x18009e9ee  mov     rdi, [rsp+338h+var_260]
0x18009e9f6  mov     rax, [rdi]
0x18009e9f9  mov     rbx, [rax+38h]
0x18009e9fd  mov     rcx, [rsp+338h+var_270]; string
0x18009ea05  call    cs:__imp_WindowsDeleteString
0x18009ea0b  mov     [rsp+338h+var_270], r14
0x18009ea13  lea     rdx, [rsp+338h+var_270]
0x18009ea1b  mov     rcx, rdi
0x18009ea1e  mov     rax, rbx
0x18009ea21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea26  mov     rcx, [rsp+338h]; this
0x18009ea2e  test    eax, eax
0x18009ea30  js      loc_18009FE21
0x18009ea36  mov     rdx, r12; void *
0x18009ea39  call    ?CheckCancelEvent@UserManagerStatics@Internal@System@Windows@@AEAAJPEAX@Z; Windows::System::Internal::UserManagerStatics::CheckCancelEvent(void *)
0x18009ea3e  mov     rcx, [rsp+338h]; this
0x18009ea46  test    eax, eax
0x18009ea48  js      loc_18009FE35
0x18009ea4e  lea     rdx, [rsp+338h+var_1C8]
0x18009ea56  lea     rcx, [rsp+338h+var_230]
0x18009ea5e  call    ??$As@UIUserInternal@Implementation@Internal@System@Windows@@@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserInternal@Implementation@Internal@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::As<Windows::System::Internal::Implementation::IUserInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Implementation::IUserInternal>>)
0x18009ea63  mov     rcx, [rsp+338h]; this
0x18009ea6b  test    eax, eax
0x18009ea6d  js      loc_18009FE49
0x18009ea73  mov     rcx, [rsp+338h+var_1C8]
0x18009ea7b  mov     rax, [rcx]
0x18009ea7e  lea     rdx, [rsp+338h+var_1C0]
0x18009ea86  mov     rax, [rax+50h]
0x18009ea8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea8f  mov     rcx, [rsp+338h]; this
0x18009ea97  test    eax, eax
0x18009ea99  js      loc_18009FE5D
0x18009ea9f  mov     rcx, r15; this
0x18009eaa2  call    ?IsConnectedToXboxLive@UserManagerStatics@Internal@System@Windows@@AEAA_NXZ; Windows::System::Internal::UserManagerStatics::IsConnectedToXboxLive(void)
0x18009eaa7  test    al, al
0x18009eaa9  jz      loc_18009F45B
0x18009eaaf  lea     rcx, [rsp+338h+var_288]
0x18009eab7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009eabc  lea     r8, [rsp+338h+var_288]
0x18009eac4  lea     rdx, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5
0x18009eacb  mov     rcx, rsi
0x18009eace  call    ?Localize@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@IEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Localize(_GUID const &,void * *)
0x18009ead3  mov     rcx, [rsp+338h]; this
0x18009eadb  test    eax, eax
0x18009eadd  js      loc_18009FE71
0x18009eae3  xor     edx, edx; length
0x18009eae5  mov     rcx, [rsp+338h+var_270]; string
0x18009eaed  call    cs:__imp_WindowsGetStringRawBuffer
0x18009eaf3  mov     r8, rax; unsigned __int16 *
0x18009eaf6  mov     rdx, [rsp+338h+var_1C0]; void *
0x18009eafe  lea     rcx, [rsp+338h+var_88]; this
0x18009eb06  call    ??0AutoUserContext@Implementation@Internal@System@Windows@@QEAA@PEAXPEBG@Z; Windows::System::Internal::Implementation::AutoUserContext::AutoUserContext(void *,ushort const *)
0x18009eb0b  nop
0x18009eb0c  lea     rdx, [rsp+338h+var_1D0]
0x18009eb14  lea     rcx, [rsp+338h+var_258]
0x18009eb1c  call    ??$As@UIUserAuthenticationCallback@@@?$ComPtr@VSignInResult@Internal@System@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUserAuthenticationCallback@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::System::Internal::SignInResult>::As<IUserAuthenticationCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUserAuthenticationCallback>>)
0x18009eb21  mov     rcx, [rsp+338h]; this
0x18009eb29  test    eax, eax
0x18009eb2b  js      loc_18009FE86
0x18009eb31  mov     rcx, [rsp+338h+var_288]
0x18009eb39  mov     rax, [rcx]
0x18009eb3c  lea     r8, [rsp+338h+var_20C]
0x18009eb44  mov     rdx, [rsp+338h+var_1D0]
0x18009eb4c  mov     rax, [rax+98h]
0x18009eb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eb58  mov     rcx, [rsp+338h]; this
  ... truncated ...
```
